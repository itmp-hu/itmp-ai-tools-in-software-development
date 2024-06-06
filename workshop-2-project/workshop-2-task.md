# DineEase Admin

## A feladat bemutatása

Ebben a modulban egy admin alkalmazást kell fejlesztened, ami az első modulban elkészített backend funkcionalitásaira épül.

A backend megoldása az alábbi URL-en érhető el: http://es2025-cis.ddns.net:8081/api/v1

## Éttermek oldal

- **Cél:** Az éttermek listázása lapozás funkcióval egy táblázatban. A táblázat sorai adatokat jelenítenek meg minden étteremhez.
- **Feladatok:**
  - Az éttermek listájának fetch-elése és megjelenítése a név, a város, az országkód és az átlagos értékelések feltüntetésével.
  - Lapozás megvalósítása a nagyszámú étterem megjelenítésének kezeléséhez. Oldalanként maximum 10 elem jelenhet meg.

## Felhasználók oldal

- **Cél:** Az étteremtulajdonosok felhasználóinak listázása, valamint a részletes információk megtekintéséhez és a felhasználói státusz frissítéséhez szükséges funkciók biztosítása.
- **Feladatok:**
  - A felhasználók listázása névvel, e-mail címmel, valamint azzal, hogy aktiválva vannak-e.
  - Funkció a felhasználó aktív státuszának megváltoztatására. Az egyszerűség kedvéért ezt nem kell elküldeni a backendnek, elég a felületen frissíteni a státuszt.

## Értékelések oldal

- **Cél:** A értékelések listázása a létrehozás dátuma szerint rendezve.
- **Feladatok:**
  - Az értékelések listázása az étterem nevével, az értékelő nevével, értékelésével és az értékelés szövegével.
  - Rendezd az értékeléseket a létrehozás dátuma szerint csökkenő sorrendben. A legfrissebb értékelés legyen felül.
  - Helytakarékosság és jobb olvashatóság érdekében az értékelés szövege legyen elrejtve egy accordion mögé. Az accordion akkor nyíljon le, amikor rányomunk az értékelés sorára.
