# 03 Loxone IO Map

## 1. Přehled modulů

### Core
- 1x Miniserver Gen.2

### Extensions
- 2x Tree Extension
- 1x Air Base Extension
- 1x One-Wire Extension
- 2x Modbus Extension
- 3x Relay Extension
- 21x Dimmer Tree
- 1x Energy Meter 3-Phase Tree
- 4x Energy Meter 1-Phase

---

## 2. One-Wire čidla podlah

### One-Wire Extension
- OW01 chodba
- OW02 pracovna
- OW03 kuchyň
- OW04 obývák1
- OW05 obývák2
- OW06 chodba2
- OW07 ložnice
- OW08 pokoj
- OW09 koupelna
- OW10 sprcha
- OW11 suterén
- OW12 kalírna

### Poznámka
- Doplnit přesné adresy čidel po oživení
- Doplnit místnosti do Loxone Config jako zóny topení

---

## 3. Tree zařízení

### Touch Tree s CO2
- TT01 obývák
- TT02 kuchyň
- TT03 pracovna
- TT04 ložnice
- TT05 pokoj

### Touch Tree bez CO2
- TT06 chodba dole
- TT07 chodba nahoře
- TT08 šatna dole
- TT09 šatna nahoře
- TT10 koupelna
- TT11 sklep/chodba
- TT12 technická (volitelně)
- TT13 terasa/interiér výstup (volitelně)

### Presence Sensor Tree
- PS01 obývák
- PS02 kuchyň vstup
- PS03 kuchyň linka
- PS04 pracovna
- PS05 ložnice
- PS06 pokoj
- PS07 šatna dole
- PS08 šatna nahoře
- PS09 chodba dole
- PS10 chodba nahoře
- PS11 schody
- PS12 sklep 1
- PS13 sklep 2
- PS14 sklep 3

### Tree Smoke Alarm
- SM01 obývák
- SM02 kuchyň
- SM03 sklep

### Meteostation
- MET01 venkovní

---

## 4. Air zařízení

### Air Base
- zaplavovací čidla bezdrátová
- případné další Air senzory

### Doplnit po výběru
- AIR01 ...
- AIR02 ...
- AIR03 ...

---

## 5. Modbus linky

### Modbus Extension 1
- zařízení: SolaX X3-Hybrid-15.0-D
- linka: samostatná
- doporučené nastavení:
  - baud rate: 9600
  - format: 8N1
  - slave address: ověřit na měniči
- účel:
  - FV výkon
  - výkon do/ze sítě
  - SOC
  - baterie charge/discharge
  - EPS stav
  - alarmy

### Modbus Extension 2
- zařízení: Frapol Onyx Pride 400
- linka: samostatná
- nastavení: dle Frapol Modbus mapy
- účel:
  - řízení výkonu
  - stav
  - alarmy
  - případně bypass / boost

---

## 6. Relay Extension – rozdělení funkcí

### Relay Extension 1
- R1 žaluzie 1 up
- R2 žaluzie 1 down
- R3 žaluzie 2 up
- R4 žaluzie 2 down
- R5 žaluzie 3 up
- R6 žaluzie 3 down
- R7 žaluzie 4 up
- R8 žaluzie 4 down
- R9 žaluzie 5 up
- R10 žaluzie 5 down
- R11 žaluzie 6 up
- R12 žaluzie 6 down
- R13 žaluzie 7 up
- R14 žaluzie 7 down

### Relay Extension 2
- R1 podlaha chodba
- R2 podlaha pracovna
- R3 podlaha kuchyň
- R4 podlaha obývák1
- R5 podlaha obývák2
- R6 podlaha chodba2
- R7 podlaha ložnice
- R8 podlaha pokoj
- R9 podlaha koupelna
- R10 podlaha sprcha
- R11 podlaha suterén
- R12 podlaha kalírna
- R13 rezerva
- R14 rezerva

### Relay Extension 3
- R1 boiler enable / priorita
- R2 žebřík enable
- R3 sauna enable
- R4 master blok topení
- R5 blackout signal
- R6 venkovní dekor světla enable
- R7 pračka/sušička blokace
- R8 pomocná logika
- R9 pomocná logika
- R10 pomocná logika
- R11 rezerva
- R12 rezerva
- R13 rezerva
- R14 rezerva

---

## 7. Dimmer Tree – mapování

### Spodní část domu – bodovky
- DT01 obývák 8 bodovek
- DT02 jídelna + konferenční
- DT03 kuchyň 6 bodovek
- DT04 kuchyň 2 + chodba dole
- DT05 pracovna + šatna dole
- DT06 sprcha + spíž + rezerva

### Spodní část domu – RGBW
- DT07 obývák pásek
- DT08 kuchyň pásek
- DT09 chodba dole pásek
- DT10 pracovna pásek
- DT11 šatna dole + sprcha
- DT12 terasa pásek

### Horní box – bodovky
- DT13 chodba nahoře + koupelna bodovky
- DT14 ložnice bodovky
- DT15 pokoj + šatna nahoře bodovky

### Horní box – RGBW
- DT16 chodba nahoře pásek
- DT17 ložnice pásek
- DT18 šatna nahoře pásek
- DT19 pokoj pásek
- DT20 koupelna pásek

### Rezerva
- DT21 rezerva

---

## 8. Měření přes Loxone

### 3f meter
- EM3F01 = podlahové topení celek

### 1f metery
- EM1F01 = rekuperace
- EM1F02 = boiler
- EM1F03 = světla spodní část
- EM1F04 = světla patro

---

## 9. Signály a logické proměnné

### Vstupy / stavové proměnné
- Grid_OK
- EPS_Active
- Battery_SOC
- Battery_ChargePower
- Battery_DischargePower
- PV_Power
- Grid_ImportPower
- Grid_ExportPower
- Rekuperace_Status
- Boiler_Status
- Wallbox_Status
- Blackout_Mode
- Fire_Alarm
- Water_Alarm

### Výstupy / akce
- Enable_Boiler
- Enable_Sauna
- Enable_TowelRail
- Enable_FloorHeating
- Enable_DecorativeLights
- Wallbox_Block
- Blackout_Lighting_Mode
- Outdoor_Decor_Block