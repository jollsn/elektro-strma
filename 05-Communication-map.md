# 05 Communication Map

## 1. Hlavní komunikační topologie

### Loxone Tree
- Touch Tree
- Presence Sensor Tree
- Smoke Alarm Tree
- Meteostation
- Energy Meter 3f Tree
- Dimmer Tree

### Loxone Air
- zaplavovací čidla
- případné další bezdrátové prvky

### One-Wire
- všechna podlahová čidla

### Modbus RTU #1
- SolaX X3-Hybrid-15.0-D
- samostatná linka
- RS485
- doporučeně 9600, 8N1
- adresu ověřit na měniči

### Modbus RTU #2
- Frapol Onyx Pride 400
- samostatná linka
- nastavení dle dokumentace Frapol

---

## 2. SolaX COM port

### SolaX COM pinout
- pin 4 = 485A
- pin 5 = 485B
- pin 6 = GND
- pin 3 = +13V

### Důležité
- samostatná Modbus linka
- nezkratovat pin 3 (+13V) a pin 6 (GND)
- používat správně nakrimpovaný RJ45
- délka COM kabelu max 30m

---

## 3. SolaX Meter/CT port
- DTSU666-CT na Meter/CT port měniče
- nepatří na COM
- slouží přímo měniči pro export control a řízení baterie

### Zapojení dle SolaX
- pin 4 = 485A
- pin 5 = 485B

---

## 4. EV / Wallbox
- Loxone Wallbox – nativní komunikace v Loxone ekosystému
- řízení podle:
  - Grid import/export
  - SOC baterie
  - Blackout_Mode
  - povolení nabíjení
- při blackoutu:
  - blokace

---

## 5. Rekuperace
- Modbus RTU přes samostatný Modbus Extension
- mapovat:
  - stav
  - výkon
  - alarm
  - případně režim
  - případně boost

---

## 6. Datová síť
- samostatný rack
- router
- switch
- patch panel
- zakončení optiky
- 2x Wi-Fi AP
- 6x LAN zásuvek
- 6x kamery
- případně NVR / NAS

---

## 7. Optika
- optika do garáže
- optika do boudy
- zakončení v racku

---

## 8. Doporučení kabeláže
- Modbus: stíněný kroucený pár
- Tree: podle Loxone
- One-Wire: hvězdice / vhodná topologie dle vzdáleností
- Datová síť: samostatně od siloviny