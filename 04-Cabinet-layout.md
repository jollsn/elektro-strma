# 04 Cabinet Layout

## Rozvaděče
- R1 = Loxone / 24V / řízení (6 řad × 24 M = 144 M)
- R2 = silový / FVE / EPS (6 řad × 24 M = 144 M)

> Layout vychází z **klasických 2M RCBO**. Hlavní vypínač je **na dveřích R2** jako otočný odpojovač 4P 40A — nezabírá DIN. Odchody Non-EPS (garáž, bouda, wallbox) mají vlastní podružné rozvaděče s vlastním RCCB; v R2 jsou pouze přívodní jističe 3P MCB.
>
> **Spínací relé podlahového topení (11× Finder 39.31 = 5,5 M) jsou v R1**, vedle Relay Extension #2, která je řídí. Cívky jsou 24 V (z Loxone PSU & Backup), kontakty spínají 230 V topný okruh. Výhoda oproti modulovým stykačům 1 M: poloviční šířka, 24 V cívka (žádný 230 V mezistupeň), tišší provoz.

---

## R1 – Loxone / 24V / řízení (6 řad × 24 M, využito ~130 M)

### Řada 1 — Miniserver a extensions (~20 M / 24 M)
- Miniserver Gen.2 (~8 M)
- Tree Extension #1 (~2 M)
- Tree Extension #2 (~2 M)
- Air Base Extension (~2 M)
- One-Wire Extension (~2 M)
- Modbus Extension #1 (~2 M)
- Modbus Extension #2 (~2 M)
- **Volno: ~4 M**

### Řada 2 — Dimmer Tree spodní část (~18–24 M / 24 M)
- Dimmer Tree #1 – #6 (každý ~3–4 M)

### Řada 3 — Dimmer Tree spodní část (~18–24 M / 24 M)
- Dimmer Tree #7 – #12

### Řada 4 — Relay Extensions + spínací relé podlah + svorky (21,5 M / 24 M)
| Pozice | Prvek | Šířka |
|---|---|---:|
| 1 | Relay Extension #1 (žaluzie) | 4 M |
| 2 | Relay Extension #2 (podlahové topení) | 4 M |
| 3 | Relay Extension #3 (pomocná logika) | 4 M |
| 4–14 | Finder 39.31 relé P01–P11 (11 ks × 0,5 M) | 5,5 M |
| 15 | Svorky žaluzie | 2 M |
| 16 | Svorky load shedding | 2 M |
| | **Volno** | **2,5 M** |

> Finder 39.31.0.024.0060 = slim spínací relé 0,5 M, 6 A AC1, cívka 24 V AC/DC, 1 přepínací kontakt (CO), s patici. Cívky napájeny 24 V z Loxone PSU & Backup přes výstupy Relay Extension #2 (každý výstup spíná +24 V do cívky). Silová strana 230 V přichází kabely ze R2 (CYKY 3×2,5 z RCBO P01–P11 v Row 6 R2) na kontakt relé.
>
> Proudově: nejhorší zóny (P02–P05, P08, P11 — 1100 W = 4,8 A) jsou na 80 % limitu 6 A AC1. Topné rohože jsou čistě odporové, žádný rozběhový proud — pro životnost kontaktů akceptovatelné. Slabé zóny (P01, P06, P07, P09, P10) jsou pod 50 %.

### Řada 5 — Loxone PSU + svorky (24 M / 24 M)
- Loxone Power Supply & Backup 40A (~8 M)
- 24V jištění logiky (~4 M)
- Tree svorky (~4 M)
- One-Wire svorky (~2 M)
- Vstupní svorky (~4 M)
- Air / čidla / kouř / meteostanice (~2 M)

### Řada 6 — PSU 24V + EM1F + svorky pomocné logiky (~18 M / 24 M)
- 24V PSU 20A (~4 M)
- 24V PSU 25A (~6 M)
- EM1F01–04 (4× 1 M = 4 M)
- Pojistkové rozdělení 24V (~2 M)
- Svorky pomocné logiky (~4 M, propoje Relay Extension #3)
- **Volno: ~6 M** *(svorky žaluzie a load shedding přesunuty do Row 4)*

---

## Horní lokální světelná krabice
- 24V PSU 10A
- 24V PSU 15A
- Dimmer Tree #13 – #21 (poslední rezerva)

---

## R2 – silový / FVE / EPS (6 řad × 24 M, využito 129 M)

### Řada 1 — FVE, EPS, SPD + zásuvky 2NP (23 M / 24 M)
Hlavní vypínač 4P 40A je na dveřích, nezabírá DIN.

| Pozice | Prvek | Šířka |
|---|---|---:|
| 1 | SPD T1+T2 4P | 4 M |
| 2 | DTSU666-CT | 1 M |
| 3 | SolaX Grid AC jistič 4P C40A | 4 M |
| 4 | SolaX EPS AC jistič 4P C32A | 4 M |
| 5 | Sběrnicové svorky | 2 M |
| 6 | Z06 RCBO ložnice + chodba 2NP (B16A) | 2 M |
| 7 | Z07 RCBO pokoj (B16A) | 2 M |
| 8 | Z11 RCBO WC 2NP (B16A) | 2 M |
| 9 | Z12 RCBO koupelna 2NP (B16A) | 2 M |
| | **Volno** | **1 M** |

### Řada 2 — EPS technologie + EM3F + stykače blokace (23 M / 24 M)
| Pozice | Prvek | Šířka |
|---|---|---:|
| 1 | T06 RCBO Loxone 230V (B10A) | 2 M |
| 2 | T07 RCBO rack (B10A) | 2 M |
| 3 | T08 RCBO rekuperace (B10A) | 2 M |
| 4 | T09 RCBO boiler (B10A) | 2 M |
| 5 | T10 RCBO oběhové čerpadlo TUV (B10A) | 2 M |
| 6 | T11 RCBO čerpadlo jímky (C16A) | 2 M |
| 7 | EM3F01 měřič podlah 3F | 4 M |
| 8 | Pom. relé master blok topení (Eaton Z-RA230/8-22) | 1 M |
| 9 | Pom. relé sauna blokace | 1 M |
| 10 | Pom. relé žebřík blokace | 1 M |
| 11 | Pomocné relé blackout signál | 1 M |
| 12 | Pomocné relé enable boileru | 1 M |
| 13 | Pomocné relé venkovní dekor | 1 M |
| 14 | Pomocné relé pračka/sušička blok | 1 M |
| | **Volno** | **1 M** |

### Řada 3 — Kuchyň + Indukce (15 M / 24 M)
| Pozice | Prvek | Šířka |
|---|---|---:|
| 1 | K01 RCBO lednice + myčka (B16A) | 2 M |
| 2 | K02 RCBO linka kuchyň (B16A) | 2 M |
| 3 | K03 RCBO linka kuchyň pravá (B16A) | 2 M |
| 4 | K04 RCBO trouba (B16A) | 2 M |
| 5 | K05 indukce 3P MCB B16A | 3 M |
| 6 | K05 indukce RCCB 4P 30mA typ A | 4 M |
| | **Volno** | **9 M** |

> 9 M rezerva v Row 3 → snadné rozšíření o budoucí kuchyňské spotřebiče (myčka oddělit, vinotéka, varná konvice okruh, atd.).

### Řada 4 — Sauna + Žebřík + Světla + Odchody Non-EPS (24 M / 24 M)
| Pozice | Prvek | Šířka |
|---|---|---:|
| 1 | S01 RCBO radiátor koupelna (B10A) | 2 M |
| 2 | S02 sauna 3P MCB C16A | 3 M |
| 3 | S02 sauna RCCB 4P 30mA typ A | 4 M |
| 4 | S03 RCBO světla spodní (B16A) | 2 M |
| 5 | S04 RCBO světla patro (B16A) | 2 M |
| 6 | S05 RCBO exteriér (B10A) | 2 M |
| 7 | N01 garáž 3P MCB C16A | 3 M |
| 8 | N02 bouda 3P MCB C16A | 3 M |
| 9 | N03 wallbox 3P MCB C32A | 3 M |
| | **Plno** | **0 M** |

### Řada 5 — Zásuvky 1NP a sklep (22 M / 24 M)
| Pozice | Prvek | Šířka |
|---|---|---:|
| 1 | Z01 RCBO pračka + sušička (B16A) | 2 M |
| 2 | Z02 RCBO technická (B16A) | 2 M |
| 3 | Z03 RCBO sklep + kalírna (B16A) | 2 M |
| 4 | Z04 RCBO pracovna (B16A) | 2 M |
| 5 | Z05 RCBO obývák (B16A) | 2 M |
| 6 | Z08 RCBO chodba + šatna 1NP (B16A) | 2 M |
| 7 | Z09 RCBO WC 1NP (B16A) | 2 M |
| 8 | Z10 RCBO koupelna 1NP (B16A) | 2 M |
| 9 | Z13 RCBO veranda / terasa (B16A) | 2 M |
| 10 | Z14 RCBO pod schody (B16A) | 2 M |
| 11 | Z15 RCBO půda (B10A) | 2 M |
| | **Volno** | **2 M** |

### Řada 6 — Podlahy RCBO (22 M / 24 M)
Stykače jsou v R1 Row 4. Sem jen RCBO podlah.

| Pozice | Prvek | Šířka |
|---|---|---:|
| 1 | P01 RCBO předsíň (B10A) | 2 M |
| 2 | P02 RCBO pracovna (B10A) | 2 M |
| 3 | P03 RCBO kuchyň (B10A) | 2 M |
| 4 | P04 RCBO obývák (B10A) | 2 M |
| 5 | P05 RCBO jídelna (B10A) | 2 M |
| 6 | P06 RCBO chodba 2NP (B10A) | 2 M |
| 7 | P07 RCBO ložnice (B10A) | 2 M |
| 8 | P08 RCBO pokoj (B10A) | 2 M |
| 9 | P09 RCBO koupelna (B10A) | 2 M |
| 10 | P10 RCBO chodba sklep (B6A) | 2 M |
| 11 | P11 RCBO kalírna sklep (B10A) | 2 M |
| | **Volno** | **2 M** |

---

## Souhrn modulové bilance R2

| Řada | Účel | Obsazeno | Volné |
|---|---|---:|---:|
| 1 | SPD, FVE, EPS + zásuvky 2NP (4 ks) | 23 M | 1 M |
| 2 | EPS technologie + EM3F + stykače blokace | 23 M | 1 M |
| 3 | Kuchyň + Indukce | 15 M | 9 M |
| 4 | Sauna + Žebřík + Světla + Odchody Non-EPS | 24 M | 0 M |
| 5 | Zásuvky 1NP + sklep (11 ks) | 22 M | 2 M |
| 6 | Podlahy RCBO P01–P11 | 22 M | 2 M |
| **Celkem** | | **129 M** | **15 M** |

R2 má **15 M celkovou rezervu**, Row 3 nejvíc (9 M). Nejvíc obtěžké jsou Row 4 (0 M) — sem už nic nepřibude bez přepracování.

## Kabeláž R1 ↔ R2 navíc
Protože spínací relé podlah (Finder 39.31) jsou v R1 a jejich silové vstupy přicházejí z RCBO v R2 Row 6, musíme tahat 11 propojek (CYKY-J 3×2,5) mezi rozvaděči:

- R2 Row 6 P01 RCBO → R1 Row 4 Finder KP01 (kontakt) → kabel přímo do topné rohože
- Toto neplatí pokud R1 a R2 jsou vedle sebe (společný stojan) — pak jsou propojky krátké (~30 cm)
- Pokud R1 a R2 jsou v různých místnostech, je to 11 dlouhých kabelů navíc

> **Doporučení: R1 a R2 vedle sebe ve společném stojanu / místnosti.** Jinak se 11 silových kabelů mezi rozvaděči zbytečně prodlouží a vytvoří EMC zátěž v blízkosti slaboproudu R1.

---

## Logika rozdělení R2
- **Řada 1** = vstup + 2NP zásuvky (využita rezerva po vypnutí vypínače z DIN)
- **Řada 2** = mozek systému (technologie EPS, měření podlah, ovládací relé)
- **Řada 3** = velké spotřebiče kuchyně (s rezervou na rozšíření)
- **Řada 4** = silové výjimky (sauna, sluneční kolektor / žebřík, světla, odchody do vedlejších objektů)
- **Řada 5** = zásuvky 1NP + sklep (logická skupina)
- **Řada 6** = topné podlahy 1NP + 2NP + sklep (logická skupina, jen RCBO)

Řady 5 a 6 jsou "klientelové" — vše, co obsluhuje koncové zásuvky a topné rohože, je tam. Při servisu lze odpojit kompletně podlahy (Row 6) nebo zásuvky 1NP (Row 5) jednou skupinou.

---

## Podružný rozvaděč garáž
- hlavní vypínač
- SPD T2
- RCCB 4P 30mA typ A
- světla, zásuvky, vrata, kompresor / dílna
- rezerva

## Podružný rozvaděč bouda
- hlavní vypínač
- SPD T2
- RCCB 4P 30mA typ A
- světla, zásuvky, topení 1500W, čerpadlo septiku
- rezerva
