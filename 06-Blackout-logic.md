# 06 Blackout Logic

## 1. Režimy systému
- Normal mode
- Backup mode
- EPS mode
- Blackout mode

---

## 2. Při výpadku sítě – okamžitá reakce

### Vypnout ihned
- wallbox
- sauna
- podlahové topení
- elektrický žebřík
- RGBW pásky
- dekorativní exteriér
- volitelné kuchyňské velké spotřebiče podle SOC

### Ponechat
- Loxone
- rack / internet
- rekuperace
- boiler podle stavu
- lednice
- základní světla
- běžné zásuvkové okruhy domu

---

## 3. Priorita světel při blackoutu

### Priorita 1
- chodba dole
- chodba nahoře
- schodiště
- koupelna
- WC
- kuchyň základ
- technická orientace

### Priorita 2
- ložnice základ
- pokoj základ
- pracovna základ
- obývák jídelna / konferenční

### Priorita 3
- RGBW pásky
- terasa
- dekorativní scény
- venkovní efekty

---

## 4. Boiler logika
- trvale napájený okruh
- Loxone řídí povolení / preferenci
- při blackoutu může být časově / SOC omezen
- neřešit jako dlouhodobě tvrdě odpojovaný spotřebič

---

## 5. Wallbox logika
- mimo EPS
- normálně řídit podle:
  - hlavního jističe 3x25A
  - výkonu FVE
  - import/export
- při blackoutu:
  - blokace

---

## 6. Podlahové topení
- normální režim:
  - zónová regulace podle pokojových podmínek
  - možnost optimalizace dle FVE
- blackout:
  - vše vypnout

---

## 7. Sauna
- normální režim:
  - povolení přes Loxone
- blackout:
  - blokace

---

## 8. Žebřík
- normální režim:
  - podle koupelnových scén / časů / komfortu
- blackout:
  - blokace

---

## 9. Doporučené proměnné v Loxone
- Grid_OK
- EPS_Active
- Blackout_Mode
- Battery_SOC
- Battery_DischargePower
- Battery_ChargePower
- PV_Power
- Grid_ImportPower
- Grid_ExportPower
- Enable_Boiler
- Enable_TowelRail
- Enable_Sauna
- Enable_FloorHeating
- Enable_DecorativeLights
- Wallbox_Block