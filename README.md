# Telefonközpont
TTL logikai áramkörökkel 
Ez az elrendezés 4 telefon csatlakoztatását teszi lehetővé, de bővíthető 8 telefonos változatra is.
Az áramkör még fejlesztés alatt áll, néhány része nem teljesen tesztelt.
Lehetőség van az áramkörhöz riasztó egységet is kötni, de elhagyható az áramkörböl.
A csengető trafó relével van leválasztva, energiatakarékosság érdekében. De elhagyható, csökkentve az
alkatrész mennyiségét.
A beszéd-áramkör kb 28v-ról megy és a 400 ohmos tekercs csökkenti a vonali búgást, és javítja a hang minőségét.
A beszélő vonalhoz tartozó potméterrel lehet be állítani, mikor az egyik telefon fel van emelve az ki kapcsolja a
tranzisztort, és a 74ls14, 74ls04 első kapu bemenete magas állapotba kerüljön. A potmétert finomra kell hangolni
hogy át engedje az impulzusokat a tranzisztor, a gombhoz lenyomott impulzus mennyiségnek megfelelően.
74ls14 két kapuja simítja az impulzusokat, és a 74ls04 késleltető üzemmódba van. Kb fél másodperc a kapcsolási idő.
Késleltetés szükséges a nem kívánt felemeléskor keletkező impulzusok szűréséhez.
74ls04 második kapuja telefon felemelése után engedélyezi a 74ls123 és a 74ls90-et. Tárcsázáskor pl ha 6-os szám
van tárcsázva akkor a 74ls123 működésbe lép és aktiválja a 74ls90 tartóáramkörét, közben a ls90 számlálja az impulzusokat.
A számláló kimenetén létre jön a bináris kimenet, amit az ls123 utolsó impulzus hatására kb 3 másodpercig fikszálja a 
kimenetet, ez a csengetési idő. Majd a ls138 a bináris kódnak megfelelő kimenetét aktiválja, és az ahhoz tartozó logikai 
folyamatot és a relét. Mivel 6 impulzust számolt a ls90, így a ls138 9-es lába alacsonyra vált, és a 3-mas telefon reléjét
aktiválja, ezzel a csengető vonalra kapcsolva a telefont.
Figyelem! Saját szám tárcsázása károsíthatja a telefon áramkörét a váltóáram és a felvett állapot miatt! 
Az áramkör szerinti tárcsázás (megváltoztatható):
                    - 1-es telefont 4-es gomb aktiválja 
                    - 2-es telefont 5-ös gomb aktiválja 
                    - 3-es telefont 6-es gomb aktiválja 
                    - 4-es telefont 7-es gomb aktiválja
Ez még bonyolítható lehetne, hogy 2 vagy 3 számjegyet lehessen tárcsázni, esetleg dupla ennyi telefonnal. De ezt 
mikrovezérlővel egyszerűbb és alkatrész takarékosabb lenne.
