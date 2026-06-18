# 09 Bill of Materials (Kusovník)

## Použité značky a řady
- **Eaton xEffect** — modulové přístroje (MCB, RCBO, RCCB, SPD, stykače, relé) — jednotný výrobce silnoproudé části
- **Loxone** — automatizační prvky (Miniserver, Extensions, Dimmer Tree, Energy Meter, PSU)
- **Mean Well DRP** — průmyslové DIN PSU 24 V pro LED
- **Eaton P3** — otočný odpojovač na dveře (hlavní vypínač R2)
- **CHINT DTSU666** — měřič dodávaný se SolaX (komponenta měniče, nelze měnit)
- **Phoenix Contact / WAGO** — svorky a propoje

X v tabulce = stejný jako první výskyt řádků nad ním.

---

## R2 – silový / FVE / EPS

### Řada 1 — FVE, EPS, SPD + zásuvky 2NP (23 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| dveře | Hlavní vypínač | HV-R2 | ruční odpojení R2 zvenku | Eaton P3-40/I2/SVB | 4P, 40 A, otočný + sada do dveří | 0 |
| 1 | SPD T1+T2 | SPD-hlavní | přepěťová ochrana hlavního vstupu | Eaton SPB-12/280/4 | 4P, typ T1+T2, Iimp 12,5 kA, Uc 280 V | 4 |
| 2 | Měřič FVE | T04 | hlavní 3f měření pro SolaX | CHINT DTSU666-CT | 3f, RS485, MID, sada SolaX | 1 |
| 3 | MCB 4P | T02 | jistič SolaX Grid AC | Eaton PL7-C40/4 | 4P, C40 A, 10 kA | 4 |
| 4 | MCB 4P | T03 | jistič SolaX EPS AC | Eaton PL7-C32/4 | 4P, C32 A, 10 kA | 4 |
| 5 | Svorky sběrnice | — | hlavní propoj L1/L2/L3 + N + PE | Phoenix Contact UT 16 | průchozí svorka 16 mm² | 2 |
| 6 | RCBO 1+N | Z06 | ložnice + chodba 2NP zásuvky | Eaton PFL6-16/1N/B/003-A | B16 A, 30 mA, typ A, 1+N, 6 kA | 2 |
| 7 | RCBO 1+N | Z07 | pokoj zásuvky | X | X | X |
| 8 | RCBO 1+N | Z11 | WC 2NP zásuvka | X | X | X |
| 9 | RCBO 1+N | Z12 | koupelna 2NP zásuvka | X | X | X |

### Řada 2 — EPS technologie + EM3F + signální relé (23 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | RCBO 1+N | T06 | napájení Loxone Miniserveru 230 V | Eaton PFL6-10/1N/B/003-A | B10 A, 30 mA, typ A, 1+N, 6 kA | 2 |
| 2 | RCBO 1+N | T07 | datový rack | X | X | X |
| 3 | RCBO 1+N | T08 | rekuperace Frapol Onyx Pride 400 | X | X | X |
| 4 | RCBO 1+N | T09 | boiler Ariston Nuos EVO 150 | X | X | X |
| 5 | RCBO 1+N | T10 | oběhové čerpadlo TUV | X | X | X |
| 6 | RCBO 1+N | T11 | čerpadlo jímky 1100 W | Eaton PFL6-16/1N/C/003-A | C16 A, 30 mA, typ A, 1+N, 6 kA | 2 |
| 7 | Loxone měřič 3F | EM3F01 | měření podlahového topení 3f | Loxone Energy Meter 3-Phase Tree | Art.Nr. 100029, Tree, 3×80 A přes CT | 4 |
| 8 | Pom. relé | — | master blok topení | Eaton Z-RA230/8-22 | 8 A, 2NO+2NC, cívka 230 V/AC, modulové, 1M | 1 |
| 9 | Pom. relé | — | sauna blokace | X | X | X |
| 10 | Pom. relé | — | žebřík blokace | X | X | X |
| 11 | Pom. relé | — | blackout signál | X | X | X |
| 12 | Pom. relé | — | enable boileru | X | X | X |
| 13 | Pom. relé | — | venkovní dekor enable | X | X | X |
| 14 | Pom. relé | — | pračka/sušička blokace | X | X | X |

### Řada 3 — Kuchyň + Indukce (15 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | RCBO 1+N | K01 | lednice + myčka | Eaton PFL6-16/1N/B/003-A | B16 A, 30 mA, typ A, 1+N | 2 |
| 2 | RCBO 1+N | K02 | linka kuchyň (levá) | X | X | X |
| 3 | RCBO 1+N | K03 | linka kuchyň pravá | X | X | X |
| 4 | RCBO 1+N | K04 | trouba | X | X | X |
| 5 | MCB 3P | K05 | indukční varná deska 3f | Eaton PL6-B16/3 | 3P, B16 A, 6 kA | 3 |
| 6 | RCCB 4P | K05 | proudový chránič indukce | Eaton PFIM-40/4/003-A | 4P, 40 A, 30 mA, typ A | 4 |

### Řada 4 — Sauna + Žebřík + Světla + Odchody Non-EPS (24 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | RCBO 1+N | S01 | koupelnový radiátor / žebřík | Eaton PFL6-10/1N/B/003-A | B10 A, 30 mA, typ A, 1+N | 2 |
| 2 | MCB 3P | S02 | sauna Harvia Cilindro PC90E 9 kW | Eaton PL7-C16/3 | 3P, C16 A, 10 kA | 3 |
| 3 | RCCB 4P | S02 | proudový chránič sauny | Eaton PFIM-40/4/003-A | 4P, 40 A, 30 mA, typ A | 4 |
| 4 | RCBO 1+N | S03 | LED PSU spodní část | Eaton PFL6-16/1N/B/003-A | B16 A, 30 mA, typ A, 1+N | 2 |
| 5 | RCBO 1+N | S04 | LED PSU horní krabice (patro) | X | X | X |
| 6 | RCBO 1+N | S05 | exteriérové osvětlení | Eaton PFL6-10/1N/B/003-A | B10 A, 30 mA, typ A, 1+N | 2 |
| 7 | MCB 3P | N01 | přívod do R-garáž | Eaton PL7-C16/3 | 3P, C16 A, 10 kA | 3 |
| 8 | MCB 3P | N02 | přívod do R-bouda | X | X | X |
| 9 | MCB 3P | N03 | přívod wallboxu 22 kW | Eaton PL7-C32/3 | 3P, C32 A, 10 kA | 3 |

### Řada 5 — Zásuvky 1NP a sklep (22 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | RCBO 1+N | Z01 | pračka + sušička | Eaton PFL6-16/1N/B/003-A | B16 A, 30 mA, typ A, 1+N | 2 |
| 2 | RCBO 1+N | Z02 | technická zásuvka | X | X | X |
| 3 | RCBO 1+N | Z03 | sklep + kalírna zásuvky | X | X | X |
| 4 | RCBO 1+N | Z04 | pracovna zásuvky | X | X | X |
| 5 | RCBO 1+N | Z05 | obývák zásuvky | X | X | X |
| 6 | RCBO 1+N | Z08 | chodba + šatna 1NP | X | X | X |
| 7 | RCBO 1+N | Z09 | WC 1NP | X | X | X |
| 8 | RCBO 1+N | Z10 | koupelna 1NP | X | X | X |
| 9 | RCBO 1+N | Z13 | veranda / terasa | X | X | X |
| 10 | RCBO 1+N | Z14 | pod schody | X | X | X |
| 11 | RCBO 1+N | Z15 | půda zásuvka + světlo | Eaton PFL6-10/1N/B/003-A | B10 A, 30 mA, typ A, 1+N | 2 |

### Řada 6 — Podlahy RCBO P01–P11 (22 M)

Stykače podlah jsou v R1 Row 4. Sem jen RCBO.

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | RCBO 1+N | P01 | topná rohož předsíň 320 W | Eaton PFL6-10/1N/B/003-A | B10 A, 30 mA, typ A, 1+N | 2 |
| 2 | RCBO 1+N | P02 | pracovna 1100 W | X | X | X |
| 3 | RCBO 1+N | P03 | kuchyň 1100 W | X | X | X |
| 4 | RCBO 1+N | P04 | obývák 1100 W | X | X | X |
| 5 | RCBO 1+N | P05 | jídelna 1100 W | X | X | X |
| 6 | RCBO 1+N | P06 | chodba 2NP 450 W | X | X | X |
| 7 | RCBO 1+N | P07 | ložnice 750 W | X | X | X |
| 8 | RCBO 1+N | P08 | pokoj 1100 W | X | X | X |
| 9 | RCBO 1+N | P09 | koupelna 450 W | X | X | X |
| 10 | RCBO 1+N | P10 | chodba sklep 200 W | Eaton PFL6-6/1N/B/003-A | B6 A, 30 mA, typ A, 1+N | 2 |
| 11 | RCBO 1+N | P11 | kalírna sklep 1100 W | Eaton PFL6-10/1N/B/003-A | B10 A, 30 mA, typ A, 1+N | 2 |

---

## R1 – Loxone / 24V / řízení

### Řada 1 — Miniserver a extensions (~22 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | Loxone Miniserver | MS-1 | centrální řídicí jednotka | Loxone Miniserver Gen.2 | Art.Nr. 100500, Ethernet, Tree, Extension Bus | 8 |
| 2 | Loxone Tree Extension | TreeExt-1 | Touch / Presence / Smoke / Meteo / žaluzie | Loxone Tree Extension | Art.Nr. 100201, 2 větve Tree | 2 |
| 3 | Loxone Tree Extension | TreeExt-2 | Dimmer Tree #1–21 + Energy Metery | X | X | X |
| 4 | Loxone Air Base | AirBase | bezdrátová Air sběrnice (zaplav. čidla) | Loxone Air Base Extension | Art.Nr. 100202, Air 868 MHz | 2 |
| 5 | Loxone One-Wire | OWExt | 11 podlahových čidel | Loxone One-Wire Extension | Art.Nr. 100086, max 20 čidel | 4 |
| 6 | Loxone Modbus | ModbusExt-1 | Modbus RTU do SolaX X3-Hybrid | Loxone Modbus Extension | Art.Nr. 100049, RS485 | 2 |
| 7 | Loxone Modbus | ModbusExt-2 | Modbus RTU do Frapol Onyx Pride | X | X | X |

### Řada 2 — Dimmer Tree spodní část #1–6 (24 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | Loxone Dimmer Tree | DT01 | obývák bodovky 24 V (8 ks) | Loxone Dimmer Tree | Art.Nr. 200115, 4× 4 A @ 24 V | 4 |
| 2 | Loxone Dimmer Tree | DT02 | jídelna + konferenční stůl | X | X | X |
| 3 | Loxone Dimmer Tree | DT03 | kuchyň bodovky (6 ks) | X | X | X |
| 4 | Loxone Dimmer Tree | DT04 | kuchyň 2 + chodba dole | X | X | X |
| 5 | Loxone Dimmer Tree | DT05 | pracovna + šatna dole | X | X | X |
| 6 | Loxone Dimmer Tree | DT06 | sprcha + spíž + rezerva | X | X | X |

### Řada 3 — Dimmer Tree spodní část #7–12 (24 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | Loxone Dimmer Tree | DT07 | RGBW pásek obývák | Loxone Dimmer Tree | Art.Nr. 200115 | 4 |
| 2 | Loxone Dimmer Tree | DT08 | RGBW pásek kuchyň | X | X | X |
| 3 | Loxone Dimmer Tree | DT09 | RGBW pásek chodba dole | X | X | X |
| 4 | Loxone Dimmer Tree | DT10 | RGBW pásek pracovna | X | X | X |
| 5 | Loxone Dimmer Tree | DT11 | RGBW pásek šatna dole + sprcha | X | X | X |
| 6 | Loxone Dimmer Tree | DT12 | RGBW pásek terasa (venkovní) | X | X | X |

### Řada 4 — Relay Extensions + spínací relé podlah + svorky (21,5 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | Loxone Relay Extension | RelayExt-1 | 5× žaluzie (up/down) + 4 rezerva | Loxone Relay Extension | Art.Nr. 100051, 14× 5 A AC1 | 4 |
| 2 | Loxone Relay Extension | RelayExt-2 | spínání cívek relé P01–P11 + 3 rez. | X | X | X |
| 3 | Loxone Relay Extension | RelayExt-3 | boiler / sauna / žebřík / blackout / dekor | X | X | X |
| 4 | Spínací relé | KP01 | spínání rohože P01 předsíň 320 W (1,4 A) | Finder 39.31.0.024.0060 | 6 A AC1, 1× přepínací (1 CO), cívka 24 V AC/DC, s patici, 0,5 M | 0,5 |
| 5 | Spínací relé | KP02 | P02 pracovna 1100 W (4,8 A) | X | X | X |
| 6 | Spínací relé | KP03 | P03 kuchyň 1100 W (4,8 A) | X | X | X |
| 7 | Spínací relé | KP04 | P04 obývák 1100 W (4,8 A) | X | X | X |
| 8 | Spínací relé | KP05 | P05 jídelna 1100 W (4,8 A) | X | X | X |
| 9 | Spínací relé | KP06 | P06 chodba 2NP 450 W (1,9 A) | X | X | X |
| 10 | Spínací relé | KP07 | P07 ložnice 750 W (3,3 A) | X | X | X |
| 11 | Spínací relé | KP08 | P08 pokoj 1100 W (4,8 A) | X | X | X |
| 12 | Spínací relé | KP09 | P09 koupelna 450 W (1,9 A) | X | X | X |
| 13 | Spínací relé | KP10 | P10 chodba sklep 200 W (0,9 A) | X | X | X |
| 14 | Spínací relé | KP11 | P11 kalírna sklep 1100 W (4,8 A) | X | X | X |
| 15 | Svorky žaluzie | SV-ZAL | připojení 5× motoru žaluzie | Phoenix Contact UT 2,5 | průchozí svorka 2,5 mm² | 2 |
| 16 | Svorky load shedding | SV-LS | signály o blokaci spotřebičů | X | X | 2 |

> Cívky Finder 39.31 jsou napájeny 24 V z Loxone PSU & Backup přes výstupy Relay Extension #2 (každý výstup spíná +24 V do cívky relé, druhý pól cívky na společné GND). Klid: cívka odpojena = relé rozepnuto = topení vypnuto.

### Řada 5 — Loxone PSU + svorky (~24 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | Loxone PSU + záloha | PSU-Loxone | hlavní 24 V + záložní baterie pro blackout | Loxone Power Supply & Backup 40 A | Art.Nr. 100150, 24 V/40 A/960 W, 12 V/12 Ah | 8 |
| 2 | MCB 1P (24 V) | F24-1..4 | jištění 24 V větví logiky (4 ks) | Eaton PL6-B2/1 | 1P, B2 A, 6 kA | 4 |
| 3 | Svorky Tree | SV-Tree | připojení Tree kabelů | Phoenix Contact UT 2,5 | 2,5 mm² průchozí | 4 |
| 4 | Svorky One-Wire | SV-OW | připojení OW čidel | X | X | 2 |
| 5 | Svorky vstupní | SV-IN | binární vstupy z R2 | X | X | 4 |
| 6 | Svorky čidla | SV-čidla | Air / kouř / meteostanice | X | X | 2 |

### Řada 6 — PSU 24 V + EM1F + svorky (~21 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | DIN PSU 24 V | PSU-20A | LED spodní část (1. zdroj) | Mean Well DRP-480-24 | 24 V/20 A/480 W, DIN, PFC | 4 |
| 2 | DIN PSU 24 V | PSU-25A | LED spodní část (2. zdroj) | Mean Well DRP-600-24 | 24 V/25 A/600 W, DIN, PFC | 6 |
| 3 | Loxone měřič 1F | EM1F01 | spotřeba rekuperace | Loxone Energy Meter 1-Phase Tree | Art.Nr. 100093, Tree, 1f | 1 |
| 4 | Loxone měřič 1F | EM1F02 | spotřeba boileru | X | X | X |
| 5 | Loxone měřič 1F | EM1F03 | spotřeba světel spodní část | X | X | X |
| 6 | Loxone měřič 1F | EM1F04 | spotřeba světel patro | X | X | X |
| 7 | MCB 1P (24 V) | F24-5..6 | rozdělení 24 V do dalších větví | Eaton PL6-B2/1 | 1P, B2 A | 2 |
| 8 | Svorky pomocné logiky | SV-AUX | propoje Relay Extension #3 | Phoenix Contact UT 2,5 | 2,5 mm² průchozí | 4 |

Svorky žaluzie a load shedding přesunuty do Row 4 (vedle Relay Extension, logicky správně).

---

## Horní lokální světelná krabice (~16 M)

| Pozice | Typ | Název | Účel | Model | Parametry | M |
|---|---|---|---|---|---|---:|
| 1 | DIN PSU 24 V | PSU-10A-H | LED v patře (1. zdroj) | Mean Well DRP-240-24 | 24 V/10 A/240 W, DIN | 3 |
| 2 | DIN PSU 24 V | PSU-15A-H | LED v patře (2. zdroj) | Mean Well DRP-360-24 | 24 V/15 A/360 W, DIN | 4 |
| 3 | Loxone Dimmer Tree | DT13 | chodba nahoře + koupelna bodovky | Loxone Dimmer Tree | Art.Nr. 200115 | 4 |
| 4 | Loxone Dimmer Tree | DT14 | ložnice bodovky | X | X | X |
| 5 | Loxone Dimmer Tree | DT15 | pokoj + šatna nahoře bodovky | X | X | X |
| 6 | Loxone Dimmer Tree | DT16 | chodba nahoře pásek RGBW | X | X | X |
| 7 | Loxone Dimmer Tree | DT17 | ložnice pásek RGBW | X | X | X |
| 8 | Loxone Dimmer Tree | DT18 | šatna nahoře pásek RGBW | X | X | X |
| 9 | Loxone Dimmer Tree | DT19 | pokoj pásek RGBW | X | X | X |
| 10 | Loxone Dimmer Tree | DT20 | koupelna pásek RGBW | X | X | X |
| 11 | Loxone Dimmer Tree | DT21 | rezerva | X | X | X |

---

## Souhrnný kusovník (pro objednání)

### Eaton xEffect (silová modulová technika)
| Typ | Účel kategorie | Model | Parametry | Ks |
|---|---|---|---|---:|
| RCBO 1+N | zásuvky / kuchyň / světla / pračka (B16) | PFL6-16/1N/B/003-A | B16 A, 30 mA, typ A, 6 kA | 22 |
| RCBO 1+N | technologie / podlahy / půda / exteriér (B10) | PFL6-10/1N/B/003-A | B10 A, 30 mA, typ A, 6 kA | 18 |
| RCBO 1+N | čerpadlo jímky (C16, rozběh) | PFL6-16/1N/C/003-A | C16 A, 30 mA, typ A, 6 kA | 1 |
| RCBO 1+N | slabá podlahová zóna (B6) | PFL6-6/1N/B/003-A | B6 A, 30 mA, typ A, 6 kA | 1 |
| RCCB 4P | proudový chránič 3f (indukce, sauna) | PFIM-40/4/003-A | 4P, 40 A, 30 mA, typ A | 2 |
| MCB 3P | jistič 3f B-charakteristika (indukce) | PL6-B16/3 | 3P, B16 A, 6 kA | 1 |
| MCB 3P | jistič 3f C-char. (sauna, garáž, bouda) | PL7-C16/3 | 3P, C16 A, 10 kA | 3 |
| MCB 3P | jistič 3f wallbox | PL7-C32/3 | 3P, C32 A, 10 kA | 1 |
| MCB 4P | jistič 4P SolaX EPS | PL7-C32/4 | 4P, C32 A, 10 kA | 1 |
| MCB 4P | jistič 4P SolaX Grid | PL7-C40/4 | 4P, C40 A, 10 kA | 1 |
| MCB 1P | jištění 24 V větví v R1 | PL6-B2/1 | 1P, B2 A, 6 kA | 6 |
| SPD T1+T2 | hlavní svodič přepětí | SPB-12/280/4 | 4P, T1+T2, Iimp 12,5 kA, Uc 280 V | 1 |
| Modulové relé | signální logika R2 (blokace, povolení, signály) | Z-RA230/8-22 | 8 A, 2NO+2NC, cívka 230 V/AC, 1M | 7 |
| Hlavní vypínač | otočný odpojovač R2 do dveří | P3-40/I2/SVB | 4P, 40 A, do dveří + adaptér DIN | 1 |

**Eaton celkem: 13 modelů, 65 ks**

### Finder (spínací relé)
| Typ | Účel kategorie | Model | Parametry | Ks |
|---|---|---|---|---:|
| Slim spínací relé | spínání podlahových rohoží P01–P11 (R1 Row 4) | 39.31.0.024.0060 | 6 A AC1, 1× přepínací (CO), cívka 24 V AC/DC, s patici, 0,5 M | 11 |

### Loxone
| Typ | Účel kategorie | Model | Art.Nr. | Ks |
|---|---|---|---|---:|
| Miniserver | centrální řídicí jednotka | Miniserver Gen.2 | 100500 | 1 |
| Tree Extension | sběrnice Tree | Tree Extension | 100201 | 2 |
| Air Base | bezdrátová Air sběrnice | Air Base Extension | 100202 | 1 |
| One-Wire | sběrnice OW pro podlahová čidla | One-Wire Extension | 100086 | 1 |
| Modbus | sběrnice Modbus RTU | Modbus Extension | 100049 | 2 |
| Dimmer Tree | stmívač 4× 4 A @ 24 V | Dimmer Tree | 200115 | 21 |
| Relay Extension | 14× reléový výstup 5 A AC1 | Relay Extension | 100051 | 3 |
| Energy Meter 3F | 3-fázový měřič | Energy Meter 3-Phase Tree | 100029 | 1 |
| Energy Meter 1F | 1-fázový měřič | Energy Meter 1-Phase Tree | 100093 | 4 |
| PSU + záloha | hlavní 24 V zdroj | Power Supply & Backup 40A | 100150 | 1 |

**Loxone celkem: 10 modelů, 37 ks**

### Mean Well (DIN PSU 24 V — Eaton nedělá ekvivalent ve výkonové třídě)
| Účel | Model | Parametry | Ks |
|---|---|---|---:|
| LED napájení horní krabice (1. zdroj) | DRP-240-24 | 24 V/10 A/240 W | 1 |
| LED napájení horní krabice (2. zdroj) | DRP-360-24 | 24 V/15 A/360 W | 1 |
| LED napájení spodní část (1. zdroj) | DRP-480-24 | 24 V/20 A/480 W | 1 |
| LED napájení spodní část (2. zdroj) | DRP-600-24 | 24 V/25 A/600 W | 1 |

### Ostatní
| Účel | Model | Ks |
|---|---|---:|
| Hlavní 3f měřič FVE (sada SolaX) | CHINT DTSU666-CT | 1 |
| Svorka silová 16 mm² | Phoenix Contact UT 16 | dle potřeby |
| Svorka slaboproud 2,5 mm² | Phoenix Contact UT 2,5 | dle potřeby |

---

## Změny vůči předchozí OEZ verzi

| OEZ původně | Eaton nyní |
|---|---|
| SVBC-12,5/4-280 | SPB-12/280/4 |
| LTN-40C-4 | PL7-C40/4 |
| LTN-32C-4 | PL7-C32/4 |
| OFE-16B-1N-A030 | PFL6-16/1N/B/003-A |
| OFE-10B-1N-A030 | PFL6-10/1N/B/003-A |
| OFE-16C-1N-A030 | PFL6-16/1N/C/003-A |
| OFE-6B-1N-A030 | PFL6-6/1N/B/003-A |
| LTN-16B-3 | PL6-B16/3 |
| LTN-16C-3 | PL7-C16/3 |
| LTN-32C-3 | PL7-C32/3 |
| OFI-40-4-030A | PFIM-40/4/003-A |
| LTN-2B-1 | PL6-B2/1 |
| KSA-16-22-230 (stykač) | Finder 39.31.0.024.0060 (slim 0,5 M relé) |
| Finder 39.31.8.230.0060 (pom. relé R2) | Eaton Z-RA230/8-22 |

> Eaton **PL6** = 6 kA řada (běžná pro RD), **PL7** = 10 kA řada (vyšší zkratová odolnost — použito pro 3-fázové výstupy s vyšším I_kss). **PFL6** = RCBO 1+N v řadě 6 kA.

## Otevřené body BOM
- Ověřit přesné objednací kódy Eaton xEffect u distributora (řada se může v čase aktualizovat — kódy uvedené jsou ze současného katalogu Eaton 2024/2025)
- Potvrdit zda PFL6 (6 kA) je dostatečné pro lokální zkratovou odolnost — pokud ne, přejít na **PFL7** (10 kA, jinak stejné značení)
- Doplnit specifikaci podružných rozvaděčů R-garáž a R-bouda (rovněž Eaton xEffect)
- Potvrdit Loxone Art.Nr. dle katalogu 2025
- Mean Well DRP řada — alternativně Eaton **PSG480F24RM** (480 W) pro plnou sjednocení, ale PSG nemá variantu 25 A / 15 A / 10 A v identickém formátu

---

# Vysvětlivky pojmů a značení

## 1. Eaton modelové řady (prefix v kódu)

| Prefix | Význam | Použití |
|---|---|---|
| **PL6 / PL7** | "**P**ole-**L**ess" — řada modulových jističů MCB. Číslo = zkratová vybavovací schopnost (6 = 6 kA, 7 = 10 kA) | Klasické jističe bez chrániče |
| **PFL6 / PFL7** | "**P**ole-Less **FI**-**L**S" = MCB + RCD kombinace = RCBO (proudový chránič s jističem v jednom). 6/7 = třída 6 nebo 10 kA | Jištění s ochranou před úrazem |
| **PFIM** | "**P**ole-Less **FI** **M**odular" = samostatný proudový chránič (RCCB) | Skupinová ochrana před úrazem |
| **SPB** | "**S**urge **P**rotective **B**lock" = svodič přepětí | Ochrana proti přepětí (blesk, spínací) |
| **Z-SCH** | Z-řada "**Sch**ütz" = instalační stykač | Silové spínání (topení, ovládání) |
| **Z-RA** | Z-řada "**R**elais **A**uxiliar" = pomocné relé modulové | Signální logika, malé proudy |
| **P3** | Otočný spínač / odpojovač řada 3 | Hlavní vypínač do dveří |

## 2. Vypínací charakteristika jističe (písmeno před proudem)

Určuje, při jakém násobku jmenovitého proudu jistič rychle vybaví (krátké zkraty / okamžitý nadproud).

| Char. | Vybaví při | Vhodné pro |
|---|---|---|
| **B** | 3–5× In | odporové zátěže — zásuvky, světla, topné rohože, bojler, lednice |
| **C** | 5–10× In | indukční zátěže s rozběhovým proudem — motory, čerpadla, sauna, kompresory, garáž, wallbox |
| **D** | 10–20× In | silné motory, transformátory (obvykle průmyslové) |

> Příklad: **B16 A** = jistič 16 A s charakteristikou B. **C32 A** = jistič 32 A s charakteristikou C.

## 3. Počet pólů (kolik fází jistič / chránič přerušuje)

| Označení | Co přerušuje |
|---|---|
| **1P** | jen 1 fázi (L) — pro 1f jednoduché okruhy, kde se nuluje sběrnicí |
| **1+N** | 1 fázi + Nulový vodič — moderní RCBO, jistí jak L tak N (povinné u zásuvek dle ČSN) |
| **3P** | 3 fáze (L1, L2, L3) — 3f bez Nulu (sauna, indukce, motory) |
| **4P** | 3 fáze + Nulový (L1, L2, L3, N) — 3f s nulem (RCCB, hlavní vypínač) |

## 4. Zkratová vybavovací schopnost (kA)

| Hodnota | Co znamená |
|---|---|
| **6 kA** | jistič vydrží přerušit zkratový proud do 6000 A — standardní pro RD se vzdálenou přípojkou |
| **10 kA** | vydrží do 10000 A — pro instalace blíže trafostanice nebo s vyšším I_kss |
| **15–25 kA** | průmyslové instalace |

> Doporučení dle ČSN: ověřit hodnotu I_k na přípojce u distributora. Pro standardní RD obvykle 6 kA stačí, blíže trafostanice použít 10 kA (PL7 řada).

## 5. Proudové chrániče (RCD / RCCB / RCBO)

### Vybavovací proud (citlivost)
| Hodnota | Použití |
|---|---|
| **10 mA** | mimořádně citlivý — speciální koupelny, dětské pokoje, FVE 1f |
| **30 mA** | **standardní pro ochranu osob** — všechny koncové okruhy v domě |
| **100 mA** | skupinová ochrana — předjištění před více 30 mA chrániči |
| **300 mA** | požární ochrana (proti unikajícímu proudu, ne před úrazem) |

### Typ chrániče (na co reaguje)
| Typ | Reaguje na | Vhodné pro |
|---|---|---|
| **AC** | jen čistý střídavý reziduální proud | starší instalace, klasické zátěže |
| **A** | AC + pulzující stejnosměrnou složku | **běžný standard** — elektronika, LED, počítače, kuchyňské spotřebiče |
| **F** | A + signály z frekvenčních měničů | klimatizace, frekvenční regulace motoru, rekuperace |
| **B** | F + čistý stejnosměrný reziduální proud | wallboxy AC, FVE měniče (vstupní strana), 3f měniče s DC vstupy |

> Loxone Wallbox 22 kW má **vestavěný RCD typu B** — v R2 stačí jistič bez externího chrániče.

## 6. Přepěťové ochrany (SPD = Surge Protective Device)

| Typ | Kategorie | Co chrání | Kam patří |
|---|---|---|---|
| **T1** (B) | svodič bleskového proudu | objekt jako celek | hlavní vstup objektu, do 1 m od přípojky |
| **T2** (C) | svodič přepětí | rozvody a zařízení | hlavní rozvaděč R2 |
| **T1+T2** (B+C) | kombinovaný | obojí v jednom přístroji | hlavní rozvaděč u zástaveb bez FeZn hromosvodu |
| **T3** (D) | jemná ochrana | koncové spotřebiče | přímo u citlivého zařízení (rack, IT) |

### Parametry SPD
| Zkratka | Význam |
|---|---|
| **Iimp** | bleskový impulsní proud (např. 12,5 kA na pól) — kolik svodič ustojí při zásahu bleskem (T1) |
| **In** | jmenovitý svodový proud (T2 testovací) |
| **Uc** | maximální trvalé pracovní napětí (280 V = pracuje do 280 V trvale, vyšší napětí spustí svod) |
| **Up** | ochranná hladina napětí (zbytkové napětí po svodu — nižší = lepší ochrana) |

## 7. Stykače a relé — kategorie použití (AC1, AC3, AC15)

Říká, na jakou zátěž je stykač / relé dimenzováno.

| Kat. | Charakter zátěže | Příklad |
|---|---|---|
| **AC1** | odporová / mírně induktivní zátěž | topné rohože, žárovky, ohřívače |
| **AC3** | motorová zátěž s vysokým rozběhovým proudem | čerpadla, ventilátory, klimatizace |
| **AC7a / AC7b** | domácí spotřebiče (pračka, myčka) | malé motory |
| **AC15** | spínání AC cívek dalších stykačů / relé | ovládací obvody |

> Příklad: **16 A AC1** = stykač spíná 16 A odporové zátěže (topení) bez problému, ale motor stejného příkonu by zvládl jen do cca 5–7 A.

## 8. Konfigurace kontaktů (NO, NC, CO)

| Označení | Význam |
|---|---|
| **NO** (Normally Open) | spínací kontakt — v klidu rozpojen, při napájení cívky sepne |
| **NC** (Normally Closed) | rozpínací kontakt — v klidu sepnut, při napájení cívky rozepne |
| **CO** (Change-Over) | přepínací kontakt — má NO i NC v jednom prvku |
| **2NO+2NC** | stykač má 2× spínací + 2× rozpínací kontakty (např. 1× pro topení + 1× pro signalizaci stavu do Loxone) |

## 9. Cívka stykače / relé

| Označení | Význam |
|---|---|
| **cívka 230 V/AC** | ovládací napětí cívky je 230 V střídavé (z fáze EPS sběrnice) |
| **cívka 24 V/DC** | 24 V stejnosměrné (z Loxone PSU) |
| **cívka 24 V/AC** | 24 V střídavé (samostatný transformátor) |

> V naší instalaci: Loxone Relay Extension spíná 230 V signál → cívka stykače 230 V/AC.

## 10. Energetické a komunikační prvky

| Zkratka | Význam |
|---|---|
| **MID** | Measuring Instruments Directive — evropská certifikace přesnosti měřičů pro fakturační měření |
| **CT** | Current Transformer — proudový převodník (klipovací clamp na fázový vodič) |
| **RS485** | sériová komunikační sběrnice (využívaná pro Modbus RTU) |
| **Modbus RTU** | průmyslový protokol pro komunikaci přes RS485 — SolaX, Frapol |
| **PFC** | Power Factor Correction — aktivní kompenzace účiníku v PSU (snižuje odběr neaktivního proudu) |

## 11. Loxone specifické pojmy

| Zkratka | Význam |
|---|---|
| **Tree** | Loxone proprietární 24 V dvojvodičová sběrnice (napájení + data, max ~500 m větev) |
| **Air** | Loxone bezdrátová sběrnice 868 MHz pro mobilní / nedostupné prvky |
| **One-Wire (OW)** | sběrnice Dallas/Maxim pro teplotní čidla (DS18B20 atp.) |
| **Art.Nr.** | Artikelnummer — Loxone objednací číslo |
| **Extension Bus** | starší interní paralelní sběrnice Loxone (mezi Miniserverem a starými extensions) |

## 12. Mechanické pojmy

| Zkratka | Význam |
|---|---|
| **M** | modulová jednotka šířky DIN lišty = **17,5 mm** |
| **DIN** | normalizovaná montážní lišta 35 mm (EN 50022) |
| **AC1 / AC3** | utility category — viz bod 7 |
| **IP44 / IP67** | krytí (Ingress Protection) — odolnost proti dotyku a vodě (44 = stříkající voda, 67 = ponořeno) |

## 13. Příklady "překladu" celého označení

### Eaton PFL6-16/1N/B/003-A
| Část | Význam |
|---|---|
| PFL6 | Pole-Less FI-LS (RCBO), 6 kA řada |
| 16 | jmenovitý proud 16 A |
| 1N | 1-fázový + Nulový (1+N) |
| B | vypínací charakteristika B |
| 003 | reziduální proud 0,03 A = **30 mA** |
| A | typ RCD = **A** (AC + pulzující DC) |

### Eaton PL7-C40/4
| Část | Význam |
|---|---|
| PL7 | Pole-Less MCB, 10 kA řada |
| C40 | charakteristika C, 40 A |
| /4 | 4-pólový |

### Eaton Z-SCH230/16-22
| Část | Význam |
|---|---|
| Z-SCH | Z-řada instalační stykač (Schütz) |
| 230 | cívka 230 V/AC |
| 16 | 16 A AC1 spínací proud |
| 22 | konfigurace kontaktů: **2** NO + **2** NC |

### Eaton SPB-12/280/4
| Část | Význam |
|---|---|
| SPB | Surge Protective Block, T1+T2 |
| 12 | Iimp 12,5 kA (zaokrouhleno) |
| 280 | Uc 280 V |
| /4 | 4-pólový (TN-S síť: 3× L + N) |
