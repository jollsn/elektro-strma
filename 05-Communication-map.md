# 05 Communication Map

## 1. Hlavní komunikační topologie

### Loxone Tree
- Touch Tree (s CO2 i bez)
- Presence Sensor Tree
- Smoke Alarm Tree
- Meteostation
- Energy Meter 3F Tree (podlahové topení)
- Energy Meter 1F Tree (rekuperace, boiler, světla spodní, světla patro)
- Dimmer Tree (21× — 12 v R1, 9 v horní krabici)

### Loxone Air
- bezdrátová zaplavovací čidla
- případné další Air senzory

### One-Wire
- 11 podlahových čidel (OW01–OW11)
- topologie: hvězda z OneWire Extension

### Modbus RTU #1 (Modbus Extension #1)
- SolaX X3-Hybrid-15.0-D
- samostatná linka, RS485
- doporučeno 9600, 8N1
- slave address ověřit na měniči

### Modbus RTU #2 (Modbus Extension #2)
- Frapol Onyx Pride 400 (rekuperace)
- samostatná linka, RS485
- nastavení dle dokumentace Frapol

## 2. SolaX COM port — pinout

| Pin | Funkce |
|---|---|
| 3 | +13 V (NEZKRATOVAT s GND/pin 6) |
| 4 | RS485 A |
| 5 | RS485 B |
| 6 | GND |

Důležité:
- samostatná Modbus linka (oddělit od silnoproudu)
- nezkratovat pin 3 (+13 V) a pin 6 (GND)
- používat správně nakrimpovaný RJ45 (T568B)
- délka COM kabelu max 30 m

## 3. SolaX Meter/CT port
- DTSU666-CT na Meter/CT port měniče (NEPATŘÍ na COM)
- slouží přímo měniči pro export control a řízení baterie

### Zapojení dle SolaX
- pin 4 = 485 A
- pin 5 = 485 B
- kabel J-Y(St)Y 2×2×0,8 stíněný

## 4. EV / Wallbox

### Loxone Wallbox 22 kW
- nativní komunikace v Loxone ekosystému (LAN + Tree)
- **vestavěný RCD typu B** — v R2 stačí 3P MCB C32 A (bez externího RCCB)
- vlastní podružný rozvaděč R-wallbox

### Řízení (Loxone logika):
- Grid import/export
- SOC baterie
- PV_Power
- Blackout_Mode → blokace

### Při blackoutu:
- blokace (úplné odpojení nabíjení)

## 5. Rekuperace
- Frapol Onyx Pride 400
- Modbus RTU přes Modbus Extension #2
- mapovat: stav, výkon, alarmy, případně režim, případně boost

## 6. Datová síť
- samostatný rack v technické místnosti
- router
- PoE switch
- patch panel
- zakončení optiky (do garáže, do boudy)
- 2× Wi-Fi AP (přízemí, patro)
- 6× LAN zásuvek
- 6× IP kamera (PoE)
- případně NVR / NAS

## 7. Optika
- optika do garáže (zakončení v R-garáž)
- optika do boudy (zakončení v R-bouda)
- preferovat singlemode (SM 9/125) pro budoucnost-proof

## 8. Doporučení kabeláže
- **Modbus:** stíněný kroucený pár (Belden 9841 nebo J-Y(St)Y 2×2×0,8)
- **Tree:** podle Loxone (Loxone Tree kabel nebo J-Y(St)Y 2×2×0,8)
- **One-Wire:** hvězdice z R1, stíněný J-Y(St)Y 2×2×0,8
- **LAN:** CAT6 U/UTP; venkovní CAT6 U/FTP s přepěťovou ochranou PoE
- **Datová síť:** vést samostatně od silnoproudu (min 100 mm souběh nebo trubka)
- **Optika:** SM 9/125, vlákna 2 (jeden funkční + jedna rezerva)

## 9. Stíněné kabely — uzemnění
- Stínění Modbus a One-Wire kabelů ukončit **jednostranně na GND** v R1 (na straně Loxone)
- Stínění CT vodiče (DTSU666) podle SolaX manuálu — typicky jednostranně u měniče

## 10. Komunikační schéma (sumarizace)

```
Loxone Miniserver Gen.2
├── Tree Ext #1 ─── Touch / Presence / Smoke / Meteo / Žaluziové aktuátory
├── Tree Ext #2 ─── 21× Dimmer Tree + 5× Energy Meter (3F + 4× 1F)
├── Air Base ─── Zaplavovací čidla (bezdrátově)
├── OneWire Ext ─── 11× podlahových čidel teploty
├── Modbus Ext #1 ─── SolaX X3-Hybrid (RS485, 9600/8N1)
├── Modbus Ext #2 ─── Frapol Onyx Pride (RS485)
├── 3× Relay Ext
│   ├── #1 (R1 Row 4): 5× žaluzie up/down + 4 rezerva
│   ├── #2 (R1 Row 4): 11× cívka Finder relé podlah + 3 rezerva
│   └── #3 (R1 Row 4): boiler / sauna / žebřík / blackout / dekor enable
└── LAN (rack) ─── Wallbox, NVR, AP, Kamery
```
