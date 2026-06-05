---
title: "AUTOWORK - WoW Constructed Languages: Earthen, Nerubian, Gnomish, Common, TWW analyses; mcp-russia reaches 12 real APIs; russia-md CI syncs"
date: 2026-06-05
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository continues its rapid expansion with four new commits adding Earthen, Nerubian, Gnomish, and Common languages, The War Within data, and deep linguistic analyses including the Arathi -dar suffix and Nerubian place-name morphology. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** connects four more government APIs — ГИБДД, ЦИК РФ, ФССП, and pravo.gov.ru — bringing the total to 12 modules with real data sources out of 19 planned. **[russia-md](https://github.com/denis-gordeev/russia-md)** syncs upstream CI hardening and Node baseline updates.

## wow_constructed_languages: four new languages and The War Within

Four commits since the last round push the language count from 20 to **24 entries** and add substantial analytical depth.

### Gnomish, Common, and Drust morphological analysis (June 4)

Gnomish and Common vocabularies are expanded with example sentences. A cross-reference between Titan and Gnomish is added to the titan-forged comparative tables. The Drust **-kor/-korn** suffix receives a dedicated investigation comparing it with Vrykul **-korn** — the analysis considers shared origin vs. coincidence.

### Shath'Yar and Kalimag sentences, The War Within data (June 4)

Six constructed example sentences each for Shath'Yar and Kalimag (clearly marked non-canon) demonstrate inferred grammar. The War Within expansion data is incorporated: Earthen place names (Khaz Algar, Dornogal, Baelgrim, Skardyn) and Nerubian data with an **Azj-/Nazj-** connection analysis. Additional investigations cover:
- **Sethrak Kor- vs Drust -kor vs Vrykul -korn**: concluded coincidental
- **Common place names**: Andorhal **-hal**, Lordaeron **-on**, Alterac **-ac**, Arathi **Arath-**
- **-din** in Thoradin vs Vrykul **-inn** sound change: three analyses at Low confidence
- **Dwarven Dun-/Durn-** connection to Common Durnholde: Low-Medium confidence

### Earthen and Nerubian languages (June 5)

Two full language entries are created with `vocabulary.md`, `grammar.md`, `description.md`, and `vocabulary.html` (with IPA):
- **Earthen**: vocabulary from Khaz Algar, Dornogal, and Skardyn sources; six example sentences (Ea1–Ea6)
- **Nerubian**: vocabulary from Azj-Kahet and Azjol-Nerub; six example sentences (Nr1–Nr6)

Key analyses:
- **Eir-** connection between Earthen Eirich and Vrykul Eyir — Low-Medium confidence
- **Azj-/Nazj-** alternation between Nerubian and Naga — Low-Medium confidence
- **Skardyn Skar-** and Vrykul Skarvald/Voldskar — Low confidence
- **-kahet** suffix attested since WotLK (Ahn'kahet = Azj-Kahet) — Moderate-High confidence

The titan-forged-comparative.html is updated with Titan↔Earthen cross-reference and a restructured family tree.

### Arathi, Nefer-, and comparative table expansion (June 5)

The latest commit adds deep morphological and onomastic analysis:
- **Nefer-** between Nerubian Neferess and Tol'vir Neferset: likely shared Blizzard design inspiration from Egyptian *nfr*, not an in-universe connection
- **Ahn- vs Azj-** alternation in Nerubian place names: data insufficient; three hypotheses evaluated (different morphemes, dialectal, Aqir origin)
- **Arathi -dar** suffix: most likely from Earthen substrate borrowed by Arathi; restricted to Khaz Algar
- Arathi personal names (Faerin Lothar, Vaelisia Steelstrike, Aelric Leid) with linguistic affiliation analysis
- Earthen column added to titan-forged cross-language comparison tables
- Arathi added to toponymic strategies table
- TWW Nerubian boss names verified against Wikipedia plot summary

## mcp-russia: four more government APIs, now 12/19 modules live

A June 3 commit connects four more real data sources and brings async conversion to three existing modules:

- **ГИБДД** (gibdd): vehicle/driver check API (гибдд.рф) and accident statistics (stat.gibdd.ru)
- **ЦИК РФ** (cekrf): GAS "Vybory" election system (vybory.izbirkom.ru), HTML parsing of election results, new `spisok_vyborov` tool
- **ФССП** (fssp): bailiff debtor database (fssp.gov.ru), POST search by full name, new `spisok_regionov` tool
- **pravo.gov.ru** (publikatsii): official legal publication search with real API

Three modules (minobrnauki, rospotrebnadzor, roskomnadzor) are converted from sync to async. Six docs/examples are cleaned up with legacy tool name replacements. **pytest: 1942 passed, ruff: all passed.**

mcp-russia now has **12 modules with real API connections** out of approximately 19 planned: ЦБ РФ, Росгидромет, ФНС, Госдума, Закупки, КАД, Open-Meteo, Dadata/Rosapi, Росреестр, ГИБДД, ЦИК РФ, ФССП (+ pravo.gov.ru).

## russia-md: upstream CI maintenance

Two routine syncs with upstream markdown-validator:
- **June 4**: CI hardening from upstream
- **June 5**: Selective upstream CI Node baseline update

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
