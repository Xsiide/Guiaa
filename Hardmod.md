If you are on 10.6.0, you must downgrade your NATIVE_FIRM using a hardmod in order to directly dump and restore your NAND.

An excellent guide for the process of creating a hardmod can be found [here](https://gbatemp.net/threads/414498/).

This is a currently working implementation of the "FIRM partitions known-plaintext" exploit detailed [here](https://www.3dbrew.org/wiki/3DS_System_Flaws). Reports of successful downgrades are sparse or unconfirmed, but seeing as anyone who tries this has a hardmod and a NAND backup (hopefully multiple backups kept in multiple locations), there isn't really much that can go wrong.

This should work on both a New and Old 3DS.

Keep in mind throughout this that 10.4, 10.5, and 10.6 use the same NATIVE-FIRM. Also keep in mind that 10.3 does not have a unique NATIVE-FIRM, and we will be using the 10.2 NATIVE-FIRM.

#### What you need

* Your 10.4, 10.5, or 10.6 NAND extracted using your hardmod
* [Raugo's autofirm pack](https://mega.nz/#!8lFwxaTA!uxag4JB3wFgI6nPwrwWuwU8lKYsGxO7AjfpARr0Q8HQ) ([Mirror](https://mega.nz/#!MxMzRQKa!b3rugzgHvvMpmBkOKv_ZDW0CvZnRVnfjPpW2JSbFAx8))
* [msvcr120d.dll](https://mega.nz/#!hgswABBS!CD1lu_wh36Mp_XyUNo2ZU-6BklTUn_ugy9hLnJ2pJZk) ([Mirror](https://drive.google.com/file/d/0BzPfvjeuhqoDZGR5M21ScWtoUEk/view?usp=sharing))
* The appropriate decrypted NATIVE-FIRM CIAs which can be found downloadable from MEGA.
    
 +    [Old 3DS 10.2 - 0004013800000002 v22313](https://mega.nz/#!osNSEJyL!jqfQJlhwTqmHLxvGfRyXNNUffgM0ze3ZTLdSf7MtkMk) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDZENDVmR5QzBEMlE))    
 +    [Old 3DS 10.4 - 0004013800000002 v23341](https://mega.nz/#!Us1CFaKK!pU-bG9Esg30LINlasTP43Sei6aDNnTIzh1ojwECKOrU) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDbGNDMllpaElpaDA))    
 +    [New 3DS 10.2 - 0004013820000002 v22313](https://mega.nz/#!tg9gUJKI!3ETGUCmWB_AKYlK5mKJhfMaNJoO_0gqEMFQTi0_65eM) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDZklNUlQ2aHc1aHc))    
 +    [New 3DS 10.4 - 0004013820000002 v23341](https://mega.nz/#!t90AiCga!anu5UenuD-uEm6z14n680rQThEgViAsytWh5ZuTa_hc) ([Mirror](https://drive.google.com/open?id=0BzPfvjeuhqoDbFRnV0EtUFlma1E))

#### Instructions

1. Extract the autofirm pack to a folder of your choice
2. Place a copy of your NAND file (named `nand.bin`) in the autofirm folder
3. Download the appropriate decrypted 10.4/10.5 NATIVE-FIRM and the decrypted 10.2 NATIVE-FIRM as CIA files
4. Rename the 10.4/10.5/10.6 NATIVE_FIRM file to `firmoriginal.cia` then put it in the autofirm folder
5. Rename the 10.2 NATIVE_FIRM file to `firmnuevo.cia` then put it in the autofirm folder
6. Place the `msvcr120d.dll` file in the autofirm folder
7. Run "start.bat"
8. If everything worked, then you will have a modified `nand.bin` containing 10.2 NATIVE_FIRM on 10.4/10.5/10.6
9. Flash this `nand.bin`, you can now follow the rest of the guide as if you were on 10.3 or below.