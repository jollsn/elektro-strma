# 02 Circuit List

## Legenda
- EPS = zálohováno
- BLK = blokovat při blackoutu
- LXM-3F = Loxone 3f meter
- LXM-1F = Loxone 1f meter
- SolaX = DTSU666-CT
- Jištění je pracovní návrh
- Kabel = doporučený průřez (detail v 08-Cable-list.md)

---

## A. FVE a technologie

| ID | Okruh | Fáze | EPS | Jištění | Kabel | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|---|
| T01 | Hlavní přívod | 3f | ano | hl. vypínač 4P 40A (na dveřích R2) | 5×10 | SolaX | ne | ne | otočný odpojovač, mimo DIN |
| T02 | SolaX GRID AC | 3f | ano | 4P C40A | 5×10 | SolaX | ano | ne | dle manuálu |
| T03 | SolaX EPS AC | 3f | ano | 4P C32A | 5×10 | SolaX | ano | ne | dle manuálu |
| T04 | DTSU666-CT | 3f | ano | dle schématu | sada SolaX | SolaX | ano | ne | hlavní měření |
| T05 | Baterie DC | DC | ano | DC breaker 32A | sada SolaX | SolaX | ano | ne | dle SolaX |
| T06 | Loxone napájení 230V | 1f | ano | RCBO B10A 30mA A | 3×2,5 | - | ano | ne | |
| T07 | Datový rack / síť | 1f | ano | RCBO B10A 30mA A | 3×2,5 | - | ano | ne | |
| T08 | Rekuperace | 1f | ano | RCBO B10A 30mA A | 3×2,5 | LXM-1F | ano | ne | Modbus |
| T09 | Boiler | 1f | ano | RCBO B10A 30mA A | 3×2,5 | LXM-1F | ano | podmíněně | trvale napájený |
| T10 | Oběhové čerpadlo TUV | 1f | ano | RCBO B10A 30mA A | 3×2,5 | - | ano | ne | |
| T11 | Čerpadlo jímky | 1f | ano | RCBO C16A 30mA A | 3×2,5 | - | ano | podmíněně | 1100W, venku v chráničce |

---

## B. Kuchyň

| ID | Okruh | Fáze | EPS | Jištění | Kabel | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|---|
| K01 | Lednice + myčka | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne | sloučený okruh dle reálného seznamu |
| K02 | Linka kuchyň (levá) | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne | |
| K03 | Linka kuchyň pravá | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne | |
| K04 | Trouba | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | podmíněně | |
| K05 | Indukční varná deska | 3f | ano | 3P B16A + RCCB 4P | 5×2,5 | - | ne | podmíněně | |

---

## C. Zásuvkové okruhy

| ID | Okruh | Fáze | EPS | Jištění | Kabel | Měření | Loxone | BLK |
|---|---|---|---|---|---|---|---|---|
| Z01 | Pračka + sušička | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ano | souběh blokovat |
| Z02 | Technická zásuvka | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z03 | Sklep + kalírna zásuvky | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z04 | Pracovna zásuvky | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z05 | Obývák zásuvky | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z06 | Ložnice + chodba 2NP zásuvky | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z07 | Pokoj zásuvky | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z08 | Chodba + šatna 1NP zásuvky | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z09 | WC 1NP zásuvka | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z10 | Koupelna 1NP zásuvka | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z11 | WC 2NP zásuvka | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z12 | Koupelna 2NP zásuvka | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z13 | Veranda / terasa | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z14 | Pod schody | 1f | ano | RCBO B16A 30mA A | 3×2,5 | - | ne | ne |
| Z15 | Půda zásuvka + světlo | 1f | ano | RCBO B10A 30mA A | 3×1,5 | - | ne | ne |

---

## D. Podlahové topení

11 zón, celkem 8770 W. Všechny kabely jednotně 3×2,5 dle reálného seznamu.

| ID | Zóna | Výkon | Fáze | EPS | Jištění | Kabel | Měření | Loxone | BLK |
|---|---|---:|---|---|---|---|---|---|---|
| P01 | předsíň (chodba 1NP) | 320W | L3 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P02 | pracovna | 1100W | L1 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P03 | kuchyň | 1100W | L2 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P04 | obývák | 1100W | L1 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P05 | jídelna | 1100W | L3 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P06 | chodba 2NP | 450W | L3 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P07 | ložnice | 750W | L1 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P08 | pokoj | 1100W | L2 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P09 | koupelna | 450W | L2 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P10 | chodba sklep | 200W | L2 | ano | RCBO B6A 30mA A | 3×2,5 | LXM-3F | ano | ano |
| P11 | kalírna sklep | 1100W | L3 | ano | RCBO B10A 30mA A | 3×2,5 | LXM-3F | ano | ano |

Fázová bilance: L1 = 2950 W, L2 = 2850 W, L3 = 2970 W.

Pozn.: zóna sprcha vypuštěna (řešena v rámci P09 koupelna). Předsíň, chodba 2NP a chodba sklep jsou výkonově malé, ale kabel je v reálném seznamu sjednocený na 3×2,5 — průřez navíc, jištění zůstává dle příkonu.

---

## E. Světla a další okruhy

| ID | Okruh | Fáze | EPS | Jištění | Kabel | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|---|
| S01 | Radiátor koupelna (žebřík) | 1f | ano | RCBO B10A 30mA A | 3×2,5 | - | ano | ano | 500W (ověřit dle skutečného modelu) |
| S02 | Sauna Harvia Cilindro PC90E | 3f | ano fyzicky | 3P C16A + RCCB 4P | 5×10 | - | ano | ano | 9kW; kabel 5×10 jako volba investora |
| S03 | Světla spodní část – AC napájení zdrojů | 1f | ano | RCBO B16A 30mA A | 3×2,5 | LXM-1F | ano | částečně | sklep + přízemí + terasa |
| S04 | Světla patro – AC napájení horní krabice | 1f | ano | RCBO B16A 30mA A | 3×2,5 | LXM-1F | ano | částečně | patro |
| S05 | Exteriér doplňkové světlo | 1f | ano | RCBO B10A/B16A | 3×1,5 | v S03 | ano | ano | dle finálního dělení |

---

## F. Non-EPS okruhy

| ID | Okruh | Fáze | EPS | Jištění | Kabel | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|---|
| N01 | Garáž přívod | 3f | ne | 3P MCB C16A | 5×2,5 | - | ne | ne | RCCB je v R-garáž |
| N02 | Bouda přívod | 3f | ne | 3P MCB C16A | 5×2,5 | - | ne | ne | RCCB je v R-bouda |
| N03 | Wallbox | 3f | ne | 3P MCB C32A | 5×10 | interně | ano | ano | RCD typu B vestavěný v Loxone Wallboxu |

---

## G. Žaluzie (souhrn)

5 motorů 230V, ovládání přes Relay Extension #1 (10 výstupů z 14, zbytek rezerva).

| ID | Žaluzie | Z | Kabel |
|---|---|---|---|
| ZAL01 | pokoj | Relay Ext #1 R1/R2 | 4×1,5 |
| ZAL02 | ložnice 2NP | Relay Ext #1 R3/R4 | 4×1,5 |
| ZAL03 | obývák pravo | Relay Ext #1 R5/R6 | 4×1,5 |
| ZAL04 | obývák střed | Relay Ext #1 R7/R8 | 4×1,5 |
| ZAL05 | obývák dveře | Relay Ext #1 R9/R10 | 4×1,5 |
