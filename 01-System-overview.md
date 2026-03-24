# 01 System Overview

## 1. Architektura systému

### Hlavní části
1. Hlavní dům
2. FVE + baterie
3. Loxone řízení
4. Datová síť / rack
5. Podružný rozvaděč garáž
6. Podružný rozvaděč bouda
7. Lokální světelná krabice patro

---

## 2. Hlavní technologie

### FVE
- SolaX X3-Hybrid-15.0-D
- DTSU666-CT
- 2x string
- baterie HV, cca 23,2 kWh
- Modbus komunikace do Loxone
- whole-home backup koncept pro hlavní dům
- nutno finálně ověřit EPS topologii podle finálního schématu SolaX/projektu

### Řízení
- Loxone Miniserver Gen.2
- Tree Extension
- Air Base Extension
- One-Wire Extension
- Modbus Extension
- Relay Extension
- Dimmer Tree
- Energy Meter Tree / 1f Energy Meter

### Rekuperace
- Frapol Onyx Pride 400
- Modbus řízení

### Boiler
- Ariston Nuos EVO A+ 150 WH
- samostatný 1f okruh
- řízení/povolení přes Loxone
- netrvale neodpojovat kvůli trvalému napájení / anodě / elektronice

### Sauna
- Harvia Cilindro PC90E
- 400V
- 9 kW
- samostatný 3f okruh
- řízeno / blokováno přes Loxone

### Wallbox
- Loxone Wallbox 22 kW
- přívod CYKY 5x10
- dynamické řízení
- při blackoutu blokovat

### Další technologie
- elektrický žebřík 500W
- čerpadlo jímky 1100W
- oběhové čerpadlo TUV
- garáž vrata
- bouda topení 1500W
- bouda čerpadlo septiku

---

## 3. EPS strategie

### Na EPS:
- hlavní dům
- Loxone
- rack
- světla domu
- běžné vnitřní zásuvkové okruhy
- rekuperace
- boiler
- lednice
- kuchyň
- technologie domu

### Mimo EPS:
- garáž
- bouda
- wallbox

### Při blackoutu vypnout:
- wallbox
- sauna
- podlahové topení
- elektrický žebřík
- RGBW pásky
- dekorativní exteriér

---

## 4. Podlahové topení

### Zóny
1. chodba – 320 W
2. pracovna – 1100 W
3. kuchyň – 1100 W
4. obývák1 – 1100 W
5. obývák2 – 1100 W
6. chodba2 – 450 W
7. ložnice – 750 W
8. pokoj – 1100 W
9. koupelna – 450 W
10. sprcha – 120 W
11. suterén – 200 W
12. kalírna – 1100 W

### Celkový výkon
- 8890 W

### Senzory
- podlahová čidla: Loxone One-Wire
- prostorová čidla: Tree / Room climate / Touch Tree with CO2 dle místnosti

---

## 5. Osvětlení

### Bodovky
- 24V Dual White D110F 12W IP65
- 6W teplá + 6W studená

### LED pásky
- 24V RGBW
- návrhově doporučeno 12 W/m
- pokud bude 20 W/m, nutné přepočítat napájení a výstupy

### Koncepce
- spodní část domu: hlavní Loxone rozvaděč
- patro: lokální světelná krabice

---

## 6. Vedlejší objekty

### Garáž
- mimo EPS
- vlastní podružný rozvaděč
- světla
- zásuvky
- vrata
- kompresor / dílenská zásuvka

### Bouda
- mimo EPS
- vlastní podružný rozvaděč
- světla
- zásuvky
- topení 1500W
- čerpadlo septiku