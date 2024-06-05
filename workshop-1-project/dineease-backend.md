# DineEase Backend

## Modul leírása
Ebben a modulban a DineEase szolgáltatás backend prototípusát kell létrehoznod. A backend adatokat biztosít a DineEase személyzete által kezelt admin alkalmazás számára, és a webalkalmazás biztosítja a szolgáltatást.

A backend által szolgáltatott adatok egy MySQL adatbázisban vannak tárolva. Az adatbázis elérhető a db.dineease.com címen, 3306-os porton, a megadott felhasználónévvel és jelszóval. Az adatbázis neve `competitor-YYYY`, ahol az `YYYY` a négyjegyű PIN kód.

Az adatbázis jelenleg üres. Használd a `assets/module-a/dineeasy.sql` mappában található SQL dumpot az adatok importálásához.

![DineEase](assets/images/db-diagram.png)

## Backend feladat

Több végpontot kell létrehoznod, amelyek a `https://competitor-YYYY-module-a.dineease.com/api/v1` alap URL-en lesznek elérhetők, ahol az `YYYY` a négyjegyű PIN kód. **A backendnek a 80-as porton kell figyelnie**, a `http` protokollt a szerver infrastruktúránk cseréli `https`-re a telepített verzió esetén.

A végpontok technikai részletei az [`assets/module-a/dineease.yaml`](assets/module-a/dineease.yaml) fájlban találhatók OpenAPI formátumban.

### Felhasználók

A DineEase személyzeti admin felületén lehetséges az étterem tulajdonosok felhasználóinak listázása, valamint a felhasználó aktiválása és deaktiválása.
Ehhez három végpontot kell létrehoznod:

- összes felhasználó rövid adatainak lekérése
- kiválasztott felhasználó részletes információinak lekérése
- felhasználó letiltása vagy aktiválása

### Éttermek

Az admin felületen listázni kell az éttermeket. Ehhez a következő végpontot kell megvalósítani:

- összes étterem lekérése az étterem értékeléseinek (vélemények) átlagolásával

### Tervek

A DineEase személyzete az admin alkalmazásban módosíthatja az előfizetési terveket. Ehhez a következő funkciókat kell biztosítani:

- összes terv adatainak lekérése
- kiválasztott terv frissítése

### Szerepkörök

A felhasználói szerepkörök nem módosíthatók az admin felületen, de szükséged lehet a szerepkör adatokra. Ehhez csak egy végpontot kell létrehoznod.

- összes szerepkör adatainak lekérése

### Vélemények

Az admin alkalmazásban megjeleníthetők az étterem vélemények, és a nem kívánt bejegyzések törölhetők. Ehhez két végpontot kell létrehoznod:

- összes vélemény lekérése rövid adatokkal (név és város) az adott étteremről, időrendben visszafelé rendezve
- kiválasztott vélemény törlése

### Regisztráció

A DineEase weboldalán az étterem tulajdonosok regisztrálhatnak személyes adataik és az általuk kiszolgált étterem vagy éttermek adatainak megadásával. Emellett a regisztráció során meg kell adniuk a kiválasztott előfizetési tervet is.

- Regisztráció küldése, amely új étterem tulajdonos felhasználót hoz létre, beállítja a kiválasztott előfizetési tervet, és létrehoz egy vagy több étterem rekordot.
- Ügyelj a validációra, beleértve azt is, hogy ne fogadjon el több éttermet, mint amennyit a kiválasztott terv engedélyez.

### Teljesen működőképes backend megoldás

Biztosítunk egy teljesen működőképes backend megoldást a teszteléshez. A backend megoldás, amely az adatbázisodat használja, a következő címen érhető el: https://competitor-yyyy-solution.dineease.com, ahol az YYYY a négyjegyű PIN kódod.

Van egy extra végpont, amely visszaállítja az adatbázist az eredeti állapotába: POST `/api/v1/reset-db`
