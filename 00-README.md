# Smart Home + FVE + EPS + Loxone + 2 hlavní rozvaděče

Technický návrh chytré domácí elektroinstalace s integrovaným fotovoltaickým systémem a záložním napájením pro třípodlažní rodinný dům s vedlejšími objekty (garáž, bouda).

## Klíčové parametry

- **Přívod:** 3×25 A z distribuční sítě ČEZ, sazba D45D
- **FVE:** SolaX X3-Hybrid-15.0-D, 9,96 kWp pole, hybridní baterie 23,2 kWh, whole-home EPS pro hlavní dům
- **Automatizace:** Loxone Miniserver Gen.2 s Tree / Air / OneWire / Modbus / Relay / Dimmer extensions
- **Rozvaděče:** 2 hlavní, každý 6 řad × 24 modulů = **144 M kapacita**
  - **R1** — Loxone / 24 V / řízení (využito ~130 M)
  - **R2** — silový / FVE / EPS (využito 129 M)
- **Hlavní vypínač:** otočný odpojovač 4P 40 A na dveřích R2 (mimo DIN)
- **Silová modulová značka:** Eaton xEffect (PL6/PL7, PFL6, PFIM, SPB, Z-RA, P3)
- **Stykače podlah:** Finder 39.31.0.024.0060 (slim 0,5 M, cívka 24 V) v R1 Row 4

## EPS strategie

- **Na EPS:** hlavní dům, Loxone, datový rack, světla, rekuperace, boiler, lednice, kuchyň, technologie domu
- **Mimo EPS:** garáž, bouda, wallbox (vlastní podružné rozvaděče)
- **Při blackoutu vypnout:** wallbox, sauna, podlahové topení, elektrický žebřík, RGBW pásky, dekorativní exteriér

## Vedlejší objekty

- **Garáž** — podružný rozvaděč s vlastním RCCB 4P 30 mA typ A, SPD T2; přívod 3f 5×2,5 z R2
- **Bouda** — podružný rozvaděč s vlastním RCCB; přívod 3f 5×2,5 z R2
- **Wallbox** — Loxone Wallbox 22 kW s vestavěným RCD typu B; přívod 5×10 z R2

## Lokální podružné rozvaděče
- **Horní lokální světelná krabice** (patro) — DIN PSU 24 V pro LED + 9× Dimmer Tree

## Struktura dokumentace

- **00-README.md** — tento přehled
- **01-System-overview.md** — architektura, hlavní technologie, EPS strategie, podlahové topení, osvětlení
- **02-Circuit-list.md** — seznam okruhů s ID, fází, jištěním, kabelem
- **03-Loxone-io-map.md** — mapování Loxone (Tree, OW, Modbus, Relay, Dimmer)
- **04-Cabinet-layout.md** — fyzické rozložení prvků v R1 a R2 po řadách
- **05-Communication-map.md** — komunikační topologie (Tree, Air, OW, Modbus, datová síť)
- **06-Blackout-logic.md** — režimy systému, blokace, priority světel
- **07-Open-items-and-checks.md** — co je třeba ověřit / dořešit
- **08-Cable-list.md** — seznam kabelů s průřezy, kabelovými trasami
- **09-Bill-of-materials.md** — kusovník (BOM) s konkrétními modely Eaton / Loxone / Finder / Mean Well

## Status

Pracovní technický návrh. Před realizací nutná **finální kontrola autorizovanou osobou** (elektroprojektant + revizní technik), zejména:
- EPS topologie SolaX (Matebox vs externí ATS — viz 07)
- Dimenzování kabelových tras dle skutečných délek
- Zkratová odolnost na přípojce (volba PL6 6 kA vs PL7 10 kA)
- Koordinace SPD s objektovým hromosvodem (pokud je)
