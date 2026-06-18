# 07 Open Items and Checks

## 1. Vyřešené v rámci návrhu (referenční záznam)

### Kuchyň
- ✅ Indukční varná deska: 3f (Eaton PL6-B16/3 + RCCB PFIM-40/4/003-A) — kabel 5×2,5
- ✅ 2. kuchyňský okruh (K03 linka pravá) — realizován ihned, není rezerva
- ✅ Lednice + myčka sloučené do K01 (jeden okruh 3×2,5)

### Podlahové topení
- ✅ 11 zón (sprcha P10 odstraněna, sloučena do P09 koupelna)
- ✅ Předsíň = P01 (nová pojmenování chodby 1NP)
- ✅ Jídelna = P05 (nová samostatná zóna, dříve obývák2)
- ✅ Chodba sklep = P10 (přejmenováno ze suterén)
- ✅ Kalírna sklep = P11
- ✅ Všechny kabely 3×2,5 (sjednoceně)
- ✅ Spínání přes Finder 39.31.0.024.0060 (slim 0,5 M) v R1 Row 4

### Zásuvky
- ✅ Rozšířeno na 15 okruhů (z 11)
- ✅ Koupelny a WC po patrech (1NP + 2NP samostatně)
- ✅ Z08 chodba + šatna 1NP samostatně

### Žaluzie
- ✅ 5 motorů (pokoj, ložnice 2NP, obývák pravo/střed/dveře)
- ✅ Relay Extension #1: 10 z 14 výstupů obsazeno, 4 rezerva

### Silová struktura
- ✅ Hlavní vypínač 4P 40 A na dveřích R2 (Eaton P3-40/I2/SVB)
- ✅ Odchody Non-EPS bez RCCB v R2 — RCCB jsou v podružných rozvaděčích
- ✅ Wallbox: vestavěný RCD typu B, v R2 jen 3P MCB C32 A
- ✅ Volba značky: Eaton xEffect (PL6/PL7, PFL6, PFIM, SPB, Z-RA, P3)
- ✅ R2 = 6 řad × 24 M, využito 129 M, rezerva 15 M
- ✅ R1 = 6 řad × 24 M, využito ~130 M, rezerva ~14 M

---

## 2. Nutné ověřit před finálním schématem

### EPS / whole-home backup
- ❓ Potvrdit finální evropské whole-home EPS řešení pro X3-Hybrid-15.0-D
- ❓ Ověřit, zda bude potřeba:
  - externí ATS
  - Matebox (SolaX produkt)
  - jiné schválené zapojení
- ❓ Potvrdit finální zapojení N/PE/RCD podle projektu

### FVE
- ❓ Potvrdit finální stringové napětí a DC ochrany
- ❓ Potvrdit umístění DC SPD (před měničem nebo v měniči)
- ❓ Potvrdit AC SPD koordinaci s objektovým SPD (T1+T2 Eaton SPB-12/280/4)

### Osvětlení
- ❓ Potvrdit finální LED pásky 12 W/m vs 20 W/m
  - při 20 W/m přepočítat průřez DC větví (z 5×1,5 na 5×2,5)
  - případně přidat střední napájecí body
- ❓ Potvrdit napájecí výkon Mean Well PSU:
  - 24 V/10 A + 15 A v horní krabici (DRP-240 + DRP-360)
  - 24 V/20 A + 25 A v R1 Row 6 (DRP-480 + DRP-600)
  - dimenzování závisí na finálním počtu bodovek
- ❓ Potvrdit skutečné délky tras k nejvzdálenějším větvím (úbytek napětí)

### Eaton xEffect
- ❓ Potvrdit přesné objednací kódy u distributora:
  - PFL6-XX/1N/B/003-A (RCBO) — případně PFL7 pro 10 kA
  - PL6/PL7-XX/Y (MCB)
  - PFIM-40/4/003-A (RCCB)
  - SPB-12/280/4 (SPD T1+T2)
  - Z-SCH230 / Z-RA230 (stykače / relé)
- ❓ Ověřit zkratovou odolnost na přípojce → rozhodnout PL6 (6 kA) vs PL7 (10 kA)

### Loxone
- ❓ Potvrdit Art.Nr. dle aktuálního katalogu 2026:
  - Miniserver Gen.2 (100500)
  - Tree / Air / OneWire / Modbus Extension
  - Dimmer Tree (200115)
  - Relay Extension (100051)
  - Energy Meter 3-Phase Tree (100029) + 1-Phase Tree (100093)
  - Power Supply & Backup 40 A (100150)
- ❓ Potvrdit skutečný počet Touch Tree bez CO2 (zatím 8 ks)
- ❓ Potvrdit přesný počet Presence Sensor Tree (zatím 14 ks)
- ❓ Potvrdit typ room klimatických prvků (Touch Tree, Touch Tree CO2, RoomControl?)

### Finder
- ❓ Potvrdit dostupnost 39.31.0.024.0060 u distributora (FINDER ČR, ELKOV)
- ❓ Potvrdit kompatibilní patici (řada 93.01)

### Mean Well
- ❓ Potvrdit Mean Well DRP-240/360/480/600 dle EU dovozu
- ❓ Alternativně Eaton PSG (jen 240 W a 480 W exist) — pokud uživatel chce sjednotit

### Kabeláž
- ❓ Doplnit délky všech tras po měření na stavbě (08-Cable-list.md sloupec "Délka")
- ❓ Ověřit skutečný výkon radiátoru koupelna S01 — pokud >2 kW, jištění z B10A na C16A
- ❓ Potvrdit typ pohonu žaluzií (230 V vs 24 V Tree)
- ❓ Doplnit kabeláž venkovního dekorativního osvětlení (230 V vs 24 V)

### Podružné rozvaděče
- ❓ Specifikace R-garáž (Eaton sortiment, podle skutečných spotřebičů — kompresor, dílna)
- ❓ Specifikace R-bouda (topení 1500 W, čerpadlo septiku)
- ❓ Délka přívodů do R-garáž a R-bouda → ověřit úbytek napětí pro 5×2,5

---

## 3. Doporučené výstupy projektu (před realizací)
- jednopólové schéma celého domu
- rozvaděčové schéma R1 (Loxone)
- rozvaděčové schéma R2 (silový)
- schéma horní lokální světelné krabice
- schéma podružných rozvaděčů (R-garáž, R-bouda, R-wallbox)
- svorkovnicový plán R1 + R2
- kusovník (08-BOM = výchozí, doplnit ks po finálním ověření)
- seznam kabelů s délkami (08-Cable-list, doplnit délky)
- I/O mapa Loxone Config (přemapovat z 03 do reálných adres)
- blackout logika (06 → Loxone Config bloky)
- měřicí mapa (EM3F + 4× EM1F + DTSU666)

## 4. Free nástroje pro projekt
- **QElectroTech** — elektroschémata, jednopólová schémata
- **LibreOffice Calc** — kusovník, seznam kabelů
- **Inkscape / LibreOffice Draw** — layout rozvaděčů
- **diagrams.net** — bloková schémata, komunikační topologie
- **FreeCAD** — případně 3D kontrola prostoru rozvaděčů
- **Loxone Config** — finální programování (přes Loxone APP/Cloud)

---

## 5. Status check (k 2026-06)
- ✅ Návrh okruhů (02-Circuit-list)
- ✅ I/O mapa Loxone (03-Loxone-io-map)
- ✅ Layout rozvaděčů R1 + R2 (04-Cabinet-layout)
- ✅ Komunikační mapa (05-Communication-map)
- ✅ Blackout logika (06-Blackout-logic)
- ✅ Seznam kabelů s průřezy (08-Cable-list)
- ✅ Kusovník s konkrétními modely (09-Bill-of-materials)
- ⏳ Specifikace podružných rozvaděčů (R-garáž, R-bouda, R-wallbox)
- ⏳ Délky kabelových tras (po měření na stavbě)
- ⏳ Finální revize autorizovanou osobou
- ⏳ EPS topologie SolaX (Matebox / ATS)
