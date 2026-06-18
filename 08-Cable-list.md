# 08 Cable List

## Legenda
- ID = identifikátor kabelu, navazuje na okruh z 02-Circuit-list.md (T/K/Z/P/S/N) nebo modul z 03-Loxone-io-map.md
- Z = výchozí bod (rozvaděč / krabice / zařízení)
- Do = cílový bod
- Typ = typ kabelu (CYKY-J = silový s ochranným vodičem, CYKY-O bez, CYSY = pohyblivý, J-Y(St)Y = telefon/stíněný, atd.)
- Průřez = jmenovitý průřez vodičů [mm² / pár]
- Délka = orientační, finálně dle prováděcí dokumentace
- IP / prostředí = poznámka k uložení (suchá / vlhká / venku / chránička)
- Stínění = ano / ne (relevantní pro Modbus, OW, slaboproud)
- Návaznost = na který okruh / modul / port se kabel zapojuje

Pracovní průřezy vycházejí z dimenzování pro běžné délky do ~25 m a uložení B2/C dle ČSN 33 2000-5-52. Pokud bude některá trasa výrazně delší (např. >30 m), je nutné průřez přepočítat na úbytek napětí a tepelné zatížení.

---

## A. Silová páteř (R2 ↔ R1, hlavní vstup, SolaX, podružné)

| ID | Z | Do | Typ | Průřez | Délka | IP | Návaznost |
|---|---|---|---|---|---:|---|---|
| C-A01 | přípojková skříň ČEZ | R2 hlavní vypínač | CYKY-J | 5×10 | TBD | trubka / chránička | T01 |
| C-A02 | R2 jistič Grid AC | SolaX X3-Hybrid AC port | CYKY-J | 5×10 | TBD | suchá | T02 |
| C-A03 | SolaX EPS port | R2 EPS sběrnice | CYKY-J | 5×10 | TBD | suchá | T03 |
| C-A04 | DTSU666-CT | SolaX Meter port | J-Y(St)Y stín. | 2×2×0,8 | TBD | suchá, dál od silových | T04 |
| C-A05 | CT clamps | DTSU666-CT | komplet ze sady SolaX | - | TBD | clamps na hlavním přívodu | T04 |
| C-A06 | baterie HV | SolaX DC port | DC kabel SolaX (komplet) | dle dodávky | TBD | dle manuálu | T05 |
| C-A07 | R2 EPS sběrnice | R1 napájení 230V | CYKY-J | 3×2,5 | TBD | suchá | T06 |
| C-A08 | R2 EPS sběrnice | datový rack 230V | CYKY-J | 3×2,5 | TBD | suchá | T07 |
| C-A09 | R2 EPS sběrnice | rekuperace Frapol | CYKY-J | 3×2,5 | TBD | strop / podhled | T08 |
| C-A10 | R2 EPS sběrnice | boiler Ariston | CYKY-J | 3×2,5 | TBD | trvale napájený | T09 |
| C-A11 | R2 EPS sběrnice | oběhové čerpadlo TUV | CYKY-J | 3×2,5 | TBD | suchá, u boileru | T10 |
| C-A12 | R2 EPS sběrnice | čerpadlo jímky | CYKY-J | 3×2,5 | TBD | venku v chráničce / IP67 spojka | T11 |

Poznámka k SolaX 5×10: jistič Grid AC C40A a EPS AC C32A tolerují 5×6, ale 5×10 sjednocuje silovou páteř s hlavním přívodem a wallboxem a dává rezervu pro případnou výměnu měniče za vyšší výkonovou třídu.

---

## B. Vnitřní zásuvkové okruhy (R2 → koncové zásuvky)

| ID | Z | Do | Typ | Průřez | Délka | IP | Návaznost |
|---|---|---|---|---|---:|---|---|
| C-B01 | R2 | pračka + sušička | CYKY-J | 3×2,5 | TBD | sloučený okruh | Z01 |
| C-B02 | R2 | technická zásuvka | CYKY-J | 3×2,5 | TBD | suchá | Z02 |
| C-B03 | R2 | sklep + kalírna zásuvky | CYKY-J | 3×2,5 | TBD | smyčka, suterén | Z03 |
| C-B04 | R2 | pracovna zásuvky | CYKY-J | 3×2,5 | TBD | smyčka | Z04 |
| C-B05 | R2 | obývák zásuvky | CYKY-J | 3×2,5 | TBD | smyčka | Z05 |
| C-B06 | R2 | ložnice + chodba 2NP zásuvky | CYKY-J | 3×2,5 | TBD | smyčka | Z06 |
| C-B07 | R2 | pokoj zásuvky | CYKY-J | 3×2,5 | TBD | smyčka | Z07 |
| C-B08 | R2 | chodba + šatna 1NP zásuvky | CYKY-J | 3×2,5 | TBD | smyčka | Z08 |
| C-B09 | R2 | WC 1NP zásuvka | CYKY-J | 3×2,5 | TBD | mimo zónu 1/2 | Z09 |
| C-B10 | R2 | koupelna 1NP zásuvka | CYKY-J | 3×2,5 | TBD | mimo zónu 1/2 | Z10 |
| C-B11 | R2 | WC 2NP zásuvka | CYKY-J | 3×2,5 | TBD | mimo zónu 1/2 | Z11 |
| C-B12 | R2 | koupelna 2NP zásuvka | CYKY-J | 3×2,5 | TBD | mimo zónu 1/2 | Z12 |
| C-B13 | R2 | terasa / veranda | CYKY-J | 3×2,5 | TBD | IP44, chránička venku | Z13 |
| C-B14 | R2 | pod schody | CYKY-J | 3×2,5 | TBD | suchá | Z14 |
| C-B15 | R2 | půda zásuvka + světlo | CYKY-J | 3×1,5 | TBD | suchá | Z15 |

---

## C. Kuchyňské okruhy

| ID | Z | Do | Typ | Průřez | Délka | IP | Návaznost |
|---|---|---|---|---|---:|---|---|
| C-C01 | R2 | lednice + myčka | CYKY-J | 3×2,5 | TBD | sloučený okruh | K01 |
| C-C02 | R2 | linka kuchyň (levá) | CYKY-J | 3×2,5 | TBD | smyčka po lince | K02 |
| C-C03 | R2 | linka kuchyň pravá | CYKY-J | 3×2,5 | TBD | smyčka po lince | K03 |
| C-C04 | R2 | trouba | CYKY-J | 3×2,5 | TBD | samostatný | K04 |
| C-C05 | R2 | indukční varná deska | CYKY-J | 5×2,5 | TBD | 3f | K05 |

---

## D. Podlahové topení (R2 / přes stykač → topná rohož)

11 zón, všechny kabely jednotně 3×2,5 dle reálného seznamu.

| ID | Z | Do | Typ | Průřez | Délka | IP | Návaznost |
|---|---|---|---|---|---:|---|---|
| C-D01 | R2 stykač P01 | rohož předsíň (chodba 1NP) 320W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P01 |
| C-D02 | R2 stykač P02 | rohož pracovna 1100W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P02 |
| C-D03 | R2 stykač P03 | rohož kuchyň 1100W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P03 |
| C-D04 | R2 stykač P04 | rohož obývák 1100W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P04 |
| C-D05 | R2 stykač P05 | rohož jídelna 1100W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P05 |
| C-D06 | R2 stykač P06 | rohož chodba 2NP 450W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P06 |
| C-D07 | R2 stykač P07 | rohož ložnice 750W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P07 |
| C-D08 | R2 stykač P08 | rohož pokoj 1100W | CYKY-J | 3×2,5 | TBD | trubka v podlaze | P08 |
| C-D09 | R2 stykač P09 | rohož koupelna 450W | CYKY-J | 3×2,5 | TBD | koupelna, IP | P09 |
| C-D10 | R2 stykač P10 | rohož chodba sklep 200W | CYKY-J | 3×2,5 | TBD | suterén | P10 |
| C-D11 | R2 stykač P11 | rohož kalírna sklep 1100W | CYKY-J | 3×2,5 | TBD | suterén | P11 |

Poznámka: ke každé rohoži samostatný kabel od stykače (jednotlivá zóna), termostaty řešeny v Loxone přes OW čidlo. Stykače / relé pro P01–P11 jsou v R2, spínání 230V dle Relay Extension #2. Zóna sprcha vypuštěna (řešena v rámci koupelnové zóny P09). Předsíň a chodba 2NP jsou na 3×2,5 přestože výkonem stačil 3×1,5 — sjednocení průřezu zjednodušuje montáž.

---

## E. Speciální výkonové (sauna, žebřík, wallbox)

| ID | Z | Do | Typ | Průřez | Délka | IP | Návaznost |
|---|---|---|---|---|---:|---|---|
| C-E01 | R2 | radiátor koupelna (žebřík) | CYKY-J | 3×2,5 | TBD | koupelna, mimo zónu 1 | S01 |
| C-E02 | R2 (stykač sauna) | Harvia Cilindro PC90E 9kW | CYKY-J | 5×10 | TBD | suchá | S02 |
| C-E03 | R2 | Loxone Wallbox 22kW | CYKY-J | 5×10 | TBD | venku v chráničce | N03 |
| C-E04 | wallbox | datová linka do R1 | CAT6 (LAN) | 4P | TBD | s wallboxem | N03 |

Poznámka k sauně 5×10: výpočtově 13A/fázi (5×2,5 by stačil), 5×10 je volba investora — masivní rezerva a sjednocení s wallboxem a hlavním přívodem.
Poznámka k žebříku: 3×2,5 (reálný seznam) je rezerva oproti 500W modelu — pokud bude vyšší výkon (>2 kW), překontrolovat jištění S01 z B10A na C16A.

---

## F. Světla – AC napájení zdrojů 24V (R2 → R1 / horní krabice)

| ID | Z | Do | Typ | Průřez | Délka | IP | Návaznost |
|---|---|---|---|---|---:|---|---|
| C-F01 | R2 | R1 PSU 24V (spodní část) | CYKY-J | 3×2,5 | TBD | suchá | S03 |
| C-F02 | R2 | horní lokální světelná krabice | CYKY-J | 3×2,5 | TBD | strop / chránička | S04 |
| C-F03 | R2 | exteriér doplňkové AC (pokud bude 230V) | CYKY-J | 3×1,5 | TBD | chránička, IP44 | S05 |

Poznámka: pokud bude veškerý exteriér i 24V přes R1, kabel C-F03 odpadá a S05 se realizuje jako DC větev (viz sekce L).

---

## G. Vedlejší objekty – přívody (R2 → podružné rozvaděče)

| ID | Z | Do | Typ | Průřez | Délka | IP | Návaznost |
|---|---|---|---|---|---:|---|---|
| C-G01 | R2 | podružný rozvaděč garáž | CYKY-J | 5×2,5 | TBD | zemní kabel v chráničce | N01 |
| C-G02 | R2 | podružný rozvaděč bouda | CYKY-J | 5×2,5 | TBD | zemní kabel v chráničce | N02 |

Poznámka: 5×2,5 = volba investora, sedí pro jištění 3P C16A. Při skutečné délce >25 m překontrolovat úbytek napětí, zejména při zapnutí kompresoru / topení 1500 W.

---

## H. Garáž – vnitřní okruhy z podružného rozvaděče

| ID | Z | Do | Typ | Průřez | IP | Poznámka |
|---|---|---|---|---|---|---|
| C-H01 | R-garáž | světla garáž | CYKY-J | 3×1,5 | LED / zářivka | smyčka |
| C-H02 | R-garáž | zásuvky garáž 230V | CYKY-J | 3×2,5 | suchá | smyčka |
| C-H03 | R-garáž | venkovní zásuvka / IP44 | CYKY-J | 3×2,5 | IP44 | samostatně |
| C-H04 | R-garáž | dílenská 3f / kompresor | CYKY-J | 5×2,5 | suchá | samostatný okruh |
| C-H05 | R-garáž | pohon vrat | CYKY-J | 3×1,5 | suchá | dle dodavatele vrat |
| C-H06 | R-garáž | rezerva | chránička | - | - | připravit prázdnou chráničku |

---

## I. Bouda – vnitřní okruhy z podružného rozvaděče

| ID | Z | Do | Typ | Průřez | IP | Poznámka |
|---|---|---|---|---|---|---|
| C-I01 | R-bouda | světla bouda | CYKY-J | 3×1,5 | suchá / IP44 dle prostoru | smyčka |
| C-I02 | R-bouda | zásuvky bouda | CYKY-J | 3×2,5 | suchá | smyčka |
| C-I03 | R-bouda | topení 1500W | CYKY-J | 3×2,5 | suchá | samostatný okruh |
| C-I04 | R-bouda | čerpadlo septiku | CYKY-J | 3×2,5 | venku, IP67 spojka | samostatný okruh |
| C-I05 | R-bouda | venkovní zásuvka | CYKY-J | 3×2,5 | IP44 | samostatně |

---

## J. Loxone Tree (R1 / horní krabice → koncové prvky)

Loxone Tree je 2-vodičová sběrnice 24V. Doporučený kabel: Loxone Tree kabel (4×0,8 mm² stíněný, 2 páry: Tree A/B + 24V/GND), případně J-Y(St)Y 2×2×0,8 nebo CAT5e/CAT6 s vyhrazenými páry.

| ID | Z | Do | Typ | Páry | Topologie | Návaznost |
|---|---|---|---|---|---|---|
| C-J01 | R1 Tree Ext #1 | TT01–TT13 (Touch Tree, větev) | Loxone Tree | 2×2×0,8 | strom | TT01–TT13 |
| C-J02 | R1 Tree Ext #1 | PS01–PS14 (Presence Tree, větev) | Loxone Tree | 2×2×0,8 | strom | PS01–PS14 |
| C-J03 | R1 Tree Ext #2 | Smoke SM01–SM03 | Loxone Tree | 2×2×0,8 | strom | SM01–SM03 |
| C-J04 | R1 Tree Ext #2 | Meteostation MET01 | Loxone Tree | 2×2×0,8 | linka | MET01 |
| C-J05 | R1 | EM3F01 podlahy | Loxone Tree | 2×2×0,8 | linka | EM3F01 |
| C-J06 | R1 | EM1F01–04 (vč. horní krabice) | Loxone Tree | 2×2×0,8 | strom | EM1F01–04 |
| C-J07 | R1 | Dimmer Tree #1–12 (in cabinet) | Loxone Tree (interně) | - | sběrnice | DT01–DT12 |
| C-J08 | R1 | horní lokální krabice (Tree pokračování) | Loxone Tree | 2×2×0,8 | páteř | DT13–DT21 |

Doporučení: tahnout chráničku z R1 do každého patra/zóny, fyzicky rozdělit Tree linky podle Tree Extension (1 = senzorika, 2 = energ. měření / další). Délka jedné Tree větve podle Loxone do ~500 m.

---

## K. One-Wire (R1 OW Extension → podlahová čidla)

| ID | Z | Do | Typ | Stínění | Návaznost |
|---|---|---|---|---|---|
| C-K01 | R1 OW Ext | OW01 chodba | J-Y(St)Y 2×2×0,8 | ano | OW01 |
| C-K02 | R1 OW Ext | OW02 pracovna | J-Y(St)Y 2×2×0,8 | ano | OW02 |
| C-K03 | R1 OW Ext | OW03 kuchyň | J-Y(St)Y 2×2×0,8 | ano | OW03 |
| C-K04 | R1 OW Ext | OW04 obývák1 | J-Y(St)Y 2×2×0,8 | ano | OW04 |
| C-K05 | R1 OW Ext | OW05 obývák2 | J-Y(St)Y 2×2×0,8 | ano | OW05 |
| C-K06 | R1 OW Ext | OW06 chodba2 | J-Y(St)Y 2×2×0,8 | ano | OW06 |
| C-K07 | R1 OW Ext | OW07 ložnice | J-Y(St)Y 2×2×0,8 | ano | OW07 |
| C-K08 | R1 OW Ext | OW08 pokoj | J-Y(St)Y 2×2×0,8 | ano | OW08 |
| C-K09 | R1 OW Ext | OW09 koupelna | J-Y(St)Y 2×2×0,8 | ano | OW09 |
| C-K10 | R1 OW Ext | OW10 sprcha | J-Y(St)Y 2×2×0,8 | ano | OW10 |
| C-K11 | R1 OW Ext | OW11 suterén | J-Y(St)Y 2×2×0,8 | ano | OW11 |
| C-K12 | R1 OW Ext | OW12 kalírna | J-Y(St)Y 2×2×0,8 | ano | OW12 |

Topologie: doporučená hvězda z OW Extension, alternativně bus s krátkými odbočkami. Stínění připojit na GND v R1 (jednostranně).

---

## L. Modbus RTU

| ID | Z | Do | Typ | Stínění | Návaznost |
|---|---|---|---|---|---|
| C-L01 | R1 Modbus Ext #1 | SolaX COM port (RJ45 4/5/6/3) | Belden 9841 / J-Y(St)Y 2×2×0,8 | ano | SolaX |
| C-L02 | R1 Modbus Ext #2 | Frapol Onyx Pride 400 | Belden 9841 / J-Y(St)Y 2×2×0,8 | ano | Frapol |
| C-L03 | DTSU666-CT | SolaX Meter/CT port | viz C-A04 | - | nepatří na COM |

Důležité (z 05-Communication-map.md):
- SolaX COM: pin 4 = 485A, pin 5 = 485B, pin 6 = GND, pin 3 = +13V — nezkratovat pin 3 a 6
- Délka COM max 30 m
- 9600 baud, 8N1
- Modbus a Meter/CT jsou různé porty — netáhnout společně

---

## M. Dimmer Tree – 24V výstupy (R1 / horní krabice → LED)

Dimmer Tree má 4 kanály × 4 A @ 24V (96W/kanál). Pro 24V bodovky 12W (0,5A) a RGBW pásky doporučená kabeláž:
- bodovky 24V Dual White: CYSY 3×1,0 nebo 3×1,5 (větev), v silových trubkách dle ČSN
- RGBW pásek 24V (4 výstupy + společný +24V): CYSY 5×1,5

Pokud bude pásek 20 W/m místo 12 W/m, je nutné překontrolovat úbytek napětí na nejdelší větvi a případně přidat střední napájecí bod nebo zvětšit průřez na 2,5 mm².

### Spodní část (R1)

| ID | Z | Do | Typ | Průřez | Návaznost |
|---|---|---|---|---|---|
| C-M01 | DT01 | obývák 8 bodovek | CYSY | 3×1,5 | DT01 |
| C-M02 | DT02 | jídelna + konferenční bodovky | CYSY | 3×1,5 | DT02 |
| C-M03 | DT03 | kuchyň 6 bodovek | CYSY | 3×1,5 | DT03 |
| C-M04 | DT04 | kuchyň 2 + chodba dole | CYSY | 3×1,5 | DT04 |
| C-M05 | DT05 | pracovna + šatna dole | CYSY | 3×1,5 | DT05 |
| C-M06 | DT06 | sprcha + spíž + rezerva | CYSY | 3×1,5 | DT06 |
| C-M07 | DT07 | obývák pásek RGBW | CYSY | 5×1,5 | DT07 |
| C-M08 | DT08 | kuchyň pásek RGBW | CYSY | 5×1,5 | DT08 |
| C-M09 | DT09 | chodba dole pásek RGBW | CYSY | 5×1,5 | DT09 |
| C-M10 | DT10 | pracovna pásek RGBW | CYSY | 5×1,5 | DT10 |
| C-M11 | DT11 | šatna dole + sprcha pásek | CYSY | 5×1,5 | DT11 |
| C-M12 | DT12 | terasa pásek RGBW | CYSY | 5×1,5 | DT12 (venku, chránička, IP67 spojky) |

### Horní krabice

| ID | Z | Do | Typ | Průřez | Návaznost |
|---|---|---|---|---|---|
| C-M13 | DT13 | chodba nahoře + koupelna bodovky | CYSY | 3×1,5 | DT13 |
| C-M14 | DT14 | ložnice bodovky | CYSY | 3×1,5 | DT14 |
| C-M15 | DT15 | pokoj + šatna nahoře bodovky | CYSY | 3×1,5 | DT15 |
| C-M16 | DT16 | chodba nahoře pásek RGBW | CYSY | 5×1,5 | DT16 |
| C-M17 | DT17 | ložnice pásek RGBW | CYSY | 5×1,5 | DT17 |
| C-M18 | DT18 | šatna nahoře pásek RGBW | CYSY | 5×1,5 | DT18 |
| C-M19 | DT19 | pokoj pásek RGBW | CYSY | 5×1,5 | DT19 |
| C-M20 | DT20 | koupelna pásek RGBW | CYSY | 5×1,5 | DT20, IP odolnost pásku do koupelny |
| C-M21 | DT21 | rezerva | chránička | - | DT21 |

---

## N. Air (bezdrátové prvky)
- AIR01–AIRxx — zaplavovací čidla, případně další Air senzory: bez kabeláže
- Air Base Extension je pevně v R1 (linka 24V z Loxone PSU)

---

## O. Žaluzie, vrata, speciální výstupy

5 motorů žaluzií (reálný stav). Relay Extension #1 obsadí 10 z 14 výstupů, zbývají 4 výstupy jako rezerva.

| ID | Z | Do | Typ | Průřez | Návaznost |
|---|---|---|---|---|---|
| C-O01 | R1 Relay Ext #1 R1/R2 | žaluzie pokoj | CYKY-J | 4×1,5 | žaluzie 1 |
| C-O02 | R1 Relay Ext #1 R3/R4 | žaluzie ložnice 2NP | CYKY-J | 4×1,5 | žaluzie 2 |
| C-O03 | R1 Relay Ext #1 R5/R6 | žaluzie obývák pravo | CYKY-J | 4×1,5 | žaluzie 3 |
| C-O04 | R1 Relay Ext #1 R7/R8 | žaluzie obývák střed | CYKY-J | 4×1,5 | žaluzie 4 |
| C-O05 | R1 Relay Ext #1 R9/R10 | žaluzie obývák dveře | CYKY-J | 4×1,5 | žaluzie 5 |
| C-O06 | R-garáž / Relay výstup | pohon vrat řízení | dle dodavatele | - | C-H05 |

Poznámka: 230V motor žaluzií = 4 vodiče (L-up, L-down, N, PE). Pokud bude 24V SOMFY io / Tree žaluziový aktuátor, kabeláž se mění — potvrdit dle výběru pohonu.

---

## P. Datová síť (rack → koncové body)

| ID | Z | Do | Typ | Návaznost |
|---|---|---|---|---|
| C-P01 | rack patch panel | LAN zásuvka pracovna | CAT6 U/UTP | 1 z 6 LAN |
| C-P02 | rack patch panel | LAN zásuvka obývák | CAT6 U/UTP | 2 z 6 LAN |
| C-P03 | rack patch panel | LAN zásuvka ložnice | CAT6 U/UTP | 3 z 6 LAN |
| C-P04 | rack patch panel | LAN zásuvka pokoj | CAT6 U/UTP | 4 z 6 LAN |
| C-P05 | rack patch panel | LAN zásuvka TV / horní | CAT6 U/UTP | 5 z 6 LAN |
| C-P06 | rack patch panel | LAN zásuvka technická | CAT6 U/UTP | 6 z 6 LAN |
| C-P07 | rack PoE switch | Wi-Fi AP přízemí | CAT6 U/UTP | AP1 |
| C-P08 | rack PoE switch | Wi-Fi AP patro | CAT6 U/UTP | AP2 |
| C-P09 | rack PoE switch | kamera 1 | CAT6 U/FTP venku | 1 z 6 |
| C-P10 | rack PoE switch | kamera 2 | CAT6 U/FTP venku | 2 z 6 |
| C-P11 | rack PoE switch | kamera 3 | CAT6 U/FTP venku | 3 z 6 |
| C-P12 | rack PoE switch | kamera 4 | CAT6 U/FTP venku | 4 z 6 |
| C-P13 | rack PoE switch | kamera 5 | CAT6 U/FTP venku | 5 z 6 |
| C-P14 | rack PoE switch | kamera 6 | CAT6 U/FTP venku | 6 z 6 |
| C-P15 | rack | wallbox | CAT6 U/UTP | viz C-E04 |
| C-P16 | rack | R1 Miniserver | CAT6 U/UTP | Loxone LAN |

Venkovní kamerové trasy: stíněný CAT6 (U/FTP) v chráničce, mimo souběh se silnoproudem, případně přepěťová ochrana PoE.

---

## Q. Optika a páteř do vedlejších objektů

| ID | Z | Do | Typ | Návaznost |
|---|---|---|---|---|
| C-Q01 | rack | garáž (rack/AP/kamera) | optika MM 50/125 OM3 nebo SM 9/125, 2 vlákna | zakončení v racku |
| C-Q02 | rack | bouda (rack/AP/kamera) | optika MM 50/125 OM3 nebo SM 9/125, 2 vlákna | zakončení v racku |

V chráničce v zemi spolu se silovým přívodem nebo samostatnou trasou. Volba MM vs SM podle vzdálenosti — pro budoucí proof preferuji SM.

---

## R. Ochranné pospojování (info — ne samostatné okruhy)
- Hlavní pospojovací přípojnice (HOP / MET) v technické místnosti
- Doplňující pospojování koupelen (CYA 4 mm² žluto-zelený od krabice EP)
- Spoj na potrubí vody, topení, plynu (pokud je)
- Spoj na uzemnění (FeZn nebo CYY 16 mm²)

Tato část patří do samostatného dokumentu / schématu uzemnění a pospojování, zde jen pro úplnost.

---

## S. Doporučené průřezy souhrnně (sjednoceno s reálným seznamem)

| Spotřebič / okruh | Průřez | Poznámka |
|---|---|---|
| Hlavní přívod 3×25A | CYKY 5×10 | dle vzdálenosti přípojkové skříně |
| SolaX Grid AC | CYKY 5×10 | jistič C40A toleruje 5×6, 5×10 = sjednocení a rezerva |
| SolaX EPS AC | CYKY 5×10 | jistič C32A toleruje 5×6, 5×10 = sjednocení |
| Sauna 9 kW (3f) | CYKY 5×10 | volba investora, výpočtově by stačil 5×2,5 |
| Wallbox 22 kW (32A/fáze) | CYKY 5×10 | nutné |
| Indukční varná deska 3f | CYKY 5×2,5 | |
| Garáž a bouda – přívod 3f | CYKY 5×2,5 | dle vzdálenosti / spotřebičů ověřit úbytek |
| 1f zásuvky 16A | CYKY 3×2,5 | smyčka |
| Půda zásuvka + světlo (10A) | CYKY 3×1,5 | |
| Topné rohože (všechny zóny) | CYKY 3×2,5 | sjednoceně |
| Radiátor / žebřík koupelna | CYKY 3×2,5 | rezerva pro vyšší výkon |
| Trouba, bojler | CYKY 3×2,5 | |
| Rekuperace, oběhové čerpadlo TUV, čerpadlo jímky | CYKY 3×2,5 | |
| Žaluzie 230V | CYKY 4×1,5 | L-up, L-down, N, PE |
| 24V bodovka větev | CYSY 3×1,5 | dle úbytku |
| 24V RGBW pásek větev | CYSY 5×1,5 | RGBW + společný +24V |
| Tree, OW, Modbus | J-Y(St)Y 2×2×0,8 | stíněný, oddělit od silových |
| LAN | CAT6 U/UTP, venku U/FTP | mimo silnoproud |
| Optika | SM 9/125 | budoucnost-proof |

---

## T. Otevřené body kabeláže
- potvrdit délky všech tras po měření na stavbě, doplnit do sloupce "Délka"
- ověřit skutečný výkon koupelnového radiátoru (S01) — pokud >2 kW, posunout jištění z B10A na C16A
- ověřit, zda pásky budou 12 W/m nebo 20 W/m → případně přepočítat C-M07 až C-M20 na 2,5 mm² nebo přidat střední napájecí bod
- potvrdit délku přívodu do garáže a boudy → ověřit úbytek napětí pro 5×2,5
- potvrdit typ pohonu žaluzií (230V vs 24V Tree) → upravit C-O01 až C-O05
- doplnit kabeláž pro venkovní dekorativní osvětlení (jakmile se rozhodne 230V vs 24V — viz C-F03 vs DC větev)
- potvrdit typ a počet bezdrátových Air zaplavovacích čidel (bez kabeláže, ale dimenzování v dokumentu 03)
- doplnit chráničky / rezervní trubky (pod schody, půda, k venkovní stěně, k bráně) — zatím v rozpočtu, ne v kabelovém listu
