# 06 Blackout Logic

## 1. Režimy systému
- **Normal mode** — síť OK, FVE běží, baterie nabíjená/vybíjená podle algoritmu
- **Backup mode** — síť OK, ale spotřebiče sníženy (např. preventivně před výpadkem nebo dle SOC)
- **EPS mode** — síť výpadek, dům běží ze SolaX EPS + baterie
- **Blackout mode** — síť výpadek + SOC pod kritickou hodnotou → maximální úspora

## 2. Při výpadku sítě — okamžitá reakce (EPS mode)

### Vypnout ihned (Wallbox_Block / Enable_FloorHeating off / atd.)
- wallbox (vlastní R-wallbox, blokace přes Loxone Modbus)
- sauna (S02 enable signál z Relay Extension #3 → odpojení Harvia)
- podlahové topení — master blok všech 11 zón (Enable_FloorHeating off)
- elektrický žebřík (S01 enable)
- RGBW pásky (Outdoor_Decor_Block + interní RGBW zóny)
- dekorativní exteriér
- volitelné kuchyňské velké spotřebiče podle SOC (trouba K04, indukce K05)

### Ponechat
- Loxone Miniserver (T06) — záloha z PSU & Backup 12 V/12 Ah
- datový rack / internet (T07)
- rekuperace (T08, snížený výkon přes Modbus)
- boiler (T09, podmíněně dle SOC — nepřerušovat tvrdě)
- oběhové čerpadlo TUV (T10)
- lednice + myčka K01 (myčka samoblokována uživatelem)
- základní světla (priority 1 — viz níže)
- běžné zásuvkové okruhy domu (Z01–Z15)

## 3. Priorita světel při blackoutu (Blackout_Lighting_Mode)

### Priorita 1 (vždy zachovat)
- chodba dole (DT04 + S03)
- chodba nahoře (DT13 + S04)
- schodiště
- koupelna 1NP + 2NP
- WC 1NP + 2NP
- kuchyň základní svit (DT03 / DT04)
- technická orientace

### Priorita 2 (zachovat dle SOC > 30 %)
- ložnice základ (DT14 / DT17)
- pokoj základ (DT15 / DT19)
- pracovna základ (DT05 / DT10)
- obývák / jídelna / konferenční (DT01 / DT02 / DT07)

### Priorita 3 (vypnout v EPS / Blackout módu)
- RGBW pásky (DT07–DT12, DT16–DT20)
- terasa pásek (DT12)
- dekorativní scény
- venkovní efekty

## 4. Boiler logika (T09)
- trvale napájený okruh
- Loxone řídí povolení / preferenci přes pomocné relé enable v R2 Row 2
- při blackoutu může být časově / SOC omezen
- **neřešit jako dlouhodobě tvrdě odpojovaný spotřebič** (anoda + elektronika)

## 5. Wallbox logika (N03)
- mimo EPS (vlastní R-wallbox)
- normálně řídit podle:
  - hlavního jističe 3×25 A (priorita pro domácí spotřebu)
  - výkonu FVE (přebytek do auta)
  - import/export bilance
- při blackoutu:
  - blokace přes Loxone (Wallbox_Block = true)

## 6. Podlahové topení (P01–P11)
- **normální režim:**
  - zónová regulace podle pokojových čidel (Touch Tree)
  - kombinace s podlahovými čidly (OW01–OW11) — ochrana proti přetopení
  - možnost optimalizace dle FVE (Enable_FloorHeating jen při přebytku)
- **blackout:**
  - vše vypnout (master blok topení z Relay Extension #3 → blok signál pro 11× Finder relé)

## 7. Sauna (S02)
- **normální režim:**
  - povolení přes Loxone (pomocné relé sauna enable v R2 Row 2)
- **blackout:**
  - blokace (Enable_Sauna = false)

## 8. Žebřík / radiátor koupelna (S01)
- **normální režim:**
  - podle koupelnových scén / časů / komfortu
  - dle SOC při Backup mode
- **blackout:**
  - blokace (Enable_TowelRail = false)

## 9. Žaluzie (5 ks)
- **normální režim:**
  - automatika dle slunečního záření (meteostanice) / času / scén
- **blackout:**
  - povolit ruční ovládání, automatika pozastavena (ne kvůli příkonu, ale kvůli signálu Grid_OK)

## 10. Doporučené proměnné v Loxone

### Vstupy / stavy (čteno přes Modbus SolaX)
- Grid_OK
- EPS_Active
- Battery_SOC
- Battery_ChargePower
- Battery_DischargePower
- PV_Power
- Grid_ImportPower
- Grid_ExportPower
- Rekuperace_Status (Modbus Frapol)
- Boiler_Status (Loxone EM1F02)
- Wallbox_Status (Loxone Wallbox LAN)
- Blackout_Mode (interní logika)
- Fire_Alarm (Smoke Tree)
- Water_Alarm (Air Base zaplav. čidla)

### Výstupy / akce (Relay Extension #3)
- Enable_Boiler
- Enable_Sauna
- Enable_TowelRail
- Enable_FloorHeating (master blok)
- Enable_DecorativeLights
- Wallbox_Block
- Blackout_Lighting_Mode (priorita 1/2/3)
- Outdoor_Decor_Block

## 11. SOC prahy (doporučené)

| SOC | Stav | Akce |
|---|---|---|
| > 80 % | komfort | bez omezení, vše ON |
| 50–80 % | normal | wallbox podle přebytku |
| 30–50 % | úspora | priorita 2 OFF, sauna blokovat, podlaha snížit |
| 15–30 % | kritický | priorita 1 only, podlaha OFF, žebřík OFF |
| < 15 % | nouze | jen Loxone + rack + lednice + minimum světel |

> Prahy je nutné finálně vyladit podle skutečné spotřeby a kapacity baterie 23,2 kWh.
