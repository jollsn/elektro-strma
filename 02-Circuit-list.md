# 02 Circuit List

## Legenda
- EPS = zálohováno
- BLK = blokovat při blackoutu
- LXM-3F = Loxone 3f meter
- LXM-1F = Loxone 1f meter
- SolaX = DTSU666-CT
- Jištění je pracovní návrh

---

## A. FVE a technologie

| ID | Okruh | Fáze | EPS | Jištění | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|
| T01 | Hlavní přívod | 3f | ano | hlavní vypínač 4P 63A | SolaX | ne | ne | vstup R2 |
| T02 | SolaX GRID AC | 3f | ano | 4P C40A | SolaX | ano | ne | dle manuálu |
| T03 | SolaX EPS AC | 3f | ano | 4P C32A | SolaX | ano | ne | dle manuálu |
| T04 | DTSU666-CT | 3f | ano | dle schématu | SolaX | ano | ne | hlavní měření |
| T05 | Baterie DC | DC | ano | DC breaker 32A | SolaX | ano | ne | dle SolaX |
| T06 | Loxone napájení 230V | 1f | ano | RCBO B10A 30mA A | - | ano | ne | |
| T07 | Datový rack / síť | 1f | ano | RCBO B10A 30mA A | - | ano | ne | |
| T08 | Rekuperace | 1f | ano | RCBO B6A 30mA A | LXM-1F | ano | ne | Modbus |
| T09 | Boiler | 1f | ano | RCBO B10A 30mA A | LXM-1F | ano | podmíněně | trvale napájený |
| T10 | Oběhové čerpadlo TUV | 1f | ano | RCBO B6A 30mA A | - | ano | ne | |
| T11 | Čerpadlo jímky | 1f | ano | RCBO C16A 30mA A | - | ano | podmíněně | 1100W |

---

## B. Kuchyň

| ID | Okruh | Fáze | EPS | Jištění | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|
| K01 | Lednice | 1f | ano | RCBO B16A 30mA A | - | ne | ne | |
| K02 | Myčka | 1f | ano | RCBO B16A 30mA A | - | ne | ne | |
| K03 | Zásuvky linka | 1f | ano | RCBO B16A 30mA A | - | ne | ne | rezerva pro 2. okruh |
| K04 | Trouba | 1f | ano | RCBO B16A 30mA A | - | ne | podmíněně | |
| K05 | Varná deska | 2f/3f | ano | 3P B16/C16 + RCCB 4P | - | ne | podmíněně | potvrdit dle Bosch |

---

## C. Zásuvkové okruhy

| ID | Okruh | Fáze | EPS | Jištění | Měření | Loxone | BLK |
|---|---|---|---|---|---|---|---|
| Z01 | Pračka + sušička | 1f | ano | RCBO B16A 30mA A | - | ano | souběh blokovat |
| Z02 | Technická zásuvka | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z03 | Sklep chodba + kalírna zásuvky | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z04 | Pracovna zásuvky | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z05 | Obývák zásuvky | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z06 | Ložnice zásuvky | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z07 | Pokoj zásuvky | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z08 | Koupelna + chodba nahoře zásuvky | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z09 | Veranda / terasa zásuvky | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z10 | Pod schody zásuvka | 1f | ano | RCBO B16A 30mA A | - | ne | ne |
| Z11 | Půda zásuvka + světlo | 1f | ano | RCBO B10A 30mA A | - | ne | ne |

---

## D. Podlahové topení

| ID | Zóna | Výkon | Fáze | EPS | Jištění | Měření | Loxone | BLK |
|---|---|---:|---|---|---|---|---|---|
| P01 | chodba | 320W | L3 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P02 | pracovna | 1100W | L1 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P03 | kuchyň | 1100W | L2 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P04 | obývák1 | 1100W | L1 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P05 | obývák2 | 1100W | L3 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P06 | chodba2 | 450W | L3 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P07 | ložnice | 750W | L1 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P08 | pokoj | 1100W | L2 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P09 | koupelna | 450W | L2 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |
| P10 | sprcha | 120W | L2 | ano | RCBO B6A 30mA A | LXM-3F | ano | ano |
| P11 | suterén | 200W | L2 | ano | RCBO B6A 30mA A | LXM-3F | ano | ano |
| P12 | kalírna | 1100W | L3 | ano | RCBO B10A 30mA A | LXM-3F | ano | ano |

---

## E. Světla a další okruhy

| ID | Okruh | Fáze | EPS | Jištění | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|
| S01 | Žebřík koupelna | 1f | ano | RCBO B10A 30mA A | - | ano | ano | 500W |
| S02 | Sauna | 3f | ano fyzicky | 3P C16A + RCCB 4P | - | ano | ano | 9kW |
| S03 | Světla spodní část – AC napájení zdrojů | 1f | ano | RCBO B16A 30mA A | LXM-1F | ano | částečně | sklep + přízemí + terasa |
| S04 | Světla patro – AC napájení horní krabice | 1f | ano | RCBO B16A 30mA A | LXM-1F | ano | částečně | patro |
| S05 | Exteriér doplňkové světlo | 1f | ano | RCBO B10A/B16A | v S03 | ano | ano | dle finálního dělení |

---

## F. Non-EPS okruhy

| ID | Okruh | Fáze | EPS | Jištění | Měření | Loxone | BLK | Poznámka |
|---|---|---|---|---|---|---|---|---|
| N01 | Garáž přívod | 3f | ne | 3P C16A + RCCB 4P | - | ne | ne | podružný rozvaděč |
| N02 | Bouda přívod | 3f | ne | 3P C16A + RCCB 4P | - | ne | ne | podružný rozvaděč |
| N03 | Wallbox | 3f | ne | dle Loxone Wallbox manuálu | interně | ano | ano | 5x10 |