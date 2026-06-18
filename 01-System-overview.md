# System Overview

## 1. Architektura systému

### Hlavní části
1. Hlavní dům (na EPS)
2. FVE + baterie (SolaX X3-Hybrid-15.0-D + 23,2 kWh)
3. Loxone řízení (Miniserver Gen.2)
4. Datová síť / rack
5. Podružný rozvaděč garáž (mimo EPS)
6. Podružný rozvaděč bouda (mimo EPS)
7. Podružný rozvaděč wallbox (mimo EPS)
8. Lokální světelná krabice patro

## 2. Hlavní technologie

### FVE
- SolaX X3-Hybrid-15.0-D
- DTSU666-CT (sada SolaX, hlavní 3f měření)
- 2× string
- baterie HV, cca 23,2 kWh
- Modbus RTU komunikace do Loxone
- whole-home backup koncept pro hlavní dům
- nutno finálně ověřit EPS topologii podle finálního schématu SolaX (Matebox vs externí ATS — viz 07)

### Řízení
- Loxone Miniserver Gen.2
- 2× Tree Extension
- 1× Air Base Extension
- 1× One-Wire Extension
- 2× Modbus Extension
- 3× Relay Extension
- 21× Dimmer Tree
- 1× Energy Meter 3-Phase Tree (podlahové topení)
- 4× Energy Meter 1-Phase Tree (rekuperace, boiler, světla spodní, světla patro)
- Loxone Power Supply & Backup 40 A (s baterií 12 V/12 Ah)

### Rekuperace
- Frapol Onyx Pride 400
- Modbus RTU komunikace
- vlastní okruh 1f, RCBO B10 A
- napájení 3×2,5

### Boiler
- Ariston Nuos EVO A+ 150 WH (tepelné čerpadlo na TUV)
- samostatný 1f okruh
- trvalé napájení (nikdy tvrdě neodpojovat — kvůli anodě a elektronice)
- enable / priorita přes Loxone

### Sauna
- Harvia Cilindro PC90E
- 400 V, 9 kW
- samostatný 3f okruh, jištění Eaton PL7-C16/3 + RCCB PFIM-40/4/003-A
- kabel 5×10 (volba investora — rezerva)
- řízeno / blokováno přes Loxone

### Wallbox
- Loxone Wallbox 22 kW
- vlastní podružný rozvaděč R-wallbox
- vestavěný RCD typu B
- v R2 jen přívodní 3P MCB C32A
- přívod CYKY 5×10
- dynamické řízení dle FVE / SOC / Grid import
- při blackoutu blokovat

### Další technologie
- elektrický žebřík / radiátor koupelna (500 W; pokud bude vyšší výkon, ověřit jištění)
- čerpadlo jímky 1100 W (C16 A — rozběh)
- oběhové čerpadlo TUV
- garáž (vrata, kompresor, dílna)
- bouda (topení 1500 W, čerpadlo septiku)

## 3. EPS strategie

### Na EPS:
- hlavní dům
- Loxone Miniserver + extensions
- datový rack / internet
- světla domu (spodní část i patro)
- běžné vnitřní zásuvkové okruhy
- rekuperace
- boiler
- lednice + myčka (sloučený okruh K01)
- kuchyňské linky (2 okruhy K02 + K03)
- technologie domu (čerpadla, atd.)

### Mimo EPS:
- garáž (vlastní R-garáž)
- bouda (vlastní R-bouda)
- wallbox (vlastní R-wallbox)

### Při blackoutu vypnout:
- wallbox (blokace přes Loxone)
- sauna
- podlahové topení (všech 11 zón master blok)
- elektrický žebřík
- RGBW pásky
- dekorativní exteriér

## 4. Podlahové topení

### Zóny (11 ks, celkem 8770 W)
1. **P01** předsíň (chodba 1NP) – 320 W (L3)
2. **P02** pracovna – 1100 W (L1)
3. **P03** kuchyň – 1100 W (L2)
4. **P04** obývák – 1100 W (L1)
5. **P05** jídelna – 1100 W (L3)
6. **P06** chodba 2NP – 450 W (L3)
7. **P07** ložnice – 750 W (L1)
8. **P08** pokoj – 1100 W (L2)
9. **P09** koupelna – 450 W (L2)
10. **P10** chodba sklep – 200 W (L2)
11. **P11** kalírna sklep – 1100 W (L3)

Fázová bilance: L1 = 2950 W, L2 = 2850 W, L3 = 2970 W.

### Spínání
- RCBO B10A (P10 B6A) v R2 Row 6
- Spínací relé Finder 39.31.0.024.0060 (0,5 M, 6 A, cívka 24 V) v R1 Row 4
- Řízeno z Loxone Relay Extension #2

### Senzory
- podlahová čidla: Loxone One-Wire (OW01–OW11)
- prostorová čidla: Tree (Touch Tree s CO2 nebo bez) podle místnosti

## 5. Osvětlení

### Bodovky
- 24V Dual White D110F 12 W IP65
- 6 W teplá + 6 W studená

### LED pásky
- 24 V RGBW
- návrhově doporučeno 12 W/m
- pokud bude 20 W/m, nutné přepočítat napájení a výstupy

### Koncepce
- **spodní část domu:** hlavní Loxone rozvaděč R1 (12× Dimmer Tree, 2× Mean Well DRP)
- **patro:** lokální světelná krabice (9× Dimmer Tree + 1 rezerva, 2× Mean Well DRP)
- 21× Dimmer Tree celkem (1 rezerva)

## 6. Žaluzie

5 motorů (230 V, 4-vodičové ovládání):
1. pokoj
2. ložnice 2NP
3. obývák pravo
4. obývák střed
5. obývák dveře

Řízeno přes Loxone Relay Extension #1 (10 z 14 výstupů, 4 rezerva).

## 7. Vedlejší objekty

### Garáž
- mimo EPS
- vlastní podružný rozvaděč R-garáž (SPD T2, RCCB 4P 30 mA typ A, hlavní vypínač)
- přívod z R2: 3P MCB C16 A, kabel CYKY 5×2,5
- okruhy: světla, zásuvky, vrata, kompresor / dílenská zásuvka

### Bouda
- mimo EPS
- vlastní podružný rozvaděč R-bouda (SPD T2, RCCB 4P 30 mA typ A)
- přívod z R2: 3P MCB C16 A, kabel CYKY 5×2,5
- okruhy: světla, zásuvky, topení 1500 W, čerpadlo septiku
