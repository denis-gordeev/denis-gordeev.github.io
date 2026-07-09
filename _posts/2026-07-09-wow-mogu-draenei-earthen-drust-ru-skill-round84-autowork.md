---
title: "AUTOWORK - WoW Round 41: Mogu name-epithet pattern and apostrophe/hyphen compound distinction, Draenei Naaru phonological sub-system and -ari suffix, Earthen Skar- cross-language element, Drust Ath- druidic prefix; ru-skill round 84 релиз→выпуск, парсинг→разбор"
date: 2026-07-09
layout: post
---

Two repositories see new commits on July 8–9: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Round 41 with first investigations for four under-analyzed languages (Mogu, Draenei, Earthen, Drust), and **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 84 replacing релиз→выпуск, эндпоинт→конечная точка, маркетплейс→торговая площадка, парсинг→разбор.

## wow_constructed_languages: Round 41 — Four new language investigations (824 insertions, 18 files)

### Mogu: Name-Epithet Pattern and Orthographic Compound Marking

**Investigation 1: The Name-Epithet Pattern — Chinese Localization as Independent Evidence**

Eight Mogu names follow a short-word-plus-epithet pattern. Cross-referencing with Chinese localizations reveals three tiers:

| Tier | Names | Chinese–English correspondence |
|------|-------|-------------------------------|
| Strong | *Qiang* (strong→merciless), *Meng* (fierce→demented), *Ming* (bright→cunning) | Natural semantic extensions |
| Weak/poetic | *Hai* (sea→unbreakable), *Kuai* (swift→brigand) | Require metaphorical leap |
| No match | *Feng* (wind→accursed), *Xin* (heart→weaponmaster) | Clear mismatch |

Mixed hypothesis (some names from Chinese, some aesthetic) rated Medium–High plausibility; extends the known *Lei Shen* / *Mogu'shan* Chinese-origin pattern to a partial naming convention.

**Investigation 2: Apostrophe vs. Hyphen — Orthographic Marking of Compound Type**

Six compound names split between apostrophe (*Mogu'shan*, *Shan'ze*, *Lu'lin*) and hyphen (*Qin-xi*, *Jan-xi*, *Zan-Tien*). Functional, morphological, phonological, and chronological distinctions all fail to separate the two groups. Best remaining hypothesis: compound tightness — apostrophe marks fused compounds with stress shift, hyphen marks transparent compounds. Confidence Very Low–Low due to small sample.

### Draenei: Naaru Phonological Sub-System and *-ari* Suffix Analysis

**Investigation 1: Naaru Naming — A Phonological Sub-System**

All five Naaru names fit the constrained template **(C/V)'V(C)(V)** — a single initial segment, apostrophe, then vowel-initial string:

| Naaru | Pattern | Context |
|-------|---------|---------|
| A'dal | V'VC | Shattrath Naaru |
| K'ure | C'VC | Oshu'gun Naaru |
| K'ara | C'VCV | Exodar Naaru (Legion) |
| M'uru | C'VCV | Dark Naaru; Sunwell |
| O'ros | V'CVC | Exodar Naaru (TBC) |

Zero exceptions, zero parallels in Draenei compounds. Best hypothesis: Naaru self-designations transliterated into Draenei phonology from non-vocal chime/light signals (Moderate confidence for the sub-system observation).

**Investigation 2: The *-ari* Suffix and *ered* Root Family**

The *-ari* suffix (*Man'ari*) analyzed alongside *-ar* (*Eredar*) and *-ei* (*Draenei*) as a possible derivational paradigm. Three possible relationships: (1) *-ari* and *-ar* as vowel-variant of the same suffix, (2) *-ari/-ar/-ei* as vowel-grade alternation of a single nominalizer, (3) *-ari* = *-ar* + *-i* with a separate plural/adjectival marker. All remain speculative with only 3 suffix attestations across the entire language.

### Earthen: Skar- Across Earthen and Vrykul

**Investigation 2: The *Skar-* Element Across Earthen and Vrykul**

*Skar-* appears in Earthen (*Skardyn* = void-corrupted Earthen) and Vrykul (*Skarvald*, *Voldskar*). The shared Titan morpheme hypothesis (meaning "dark/corrupt/shadow") conflicts with the strong Norse/Germanic design aesthetic confound — /skɑːr/ is common in Norse-inspired naming. Norse-independent design rated Moderate–High; shared morpheme Low–Moderate. Key test: a Vrykul word using *Skar-* in a non-personal-name context with a "dark" meaning would strengthen the morpheme case.

### Drust: Ath- as Druidic Name Prefix

**Investigation 2: The *Ath-* / *Athair* Element in Thornspeaker Names**

Both *Athainne* and *Athair* are Thornspeakers sharing initial *Ath-* /əˈθ/. Irish *athair* = "father" and *ath-* = "renewal" support a druidic-prefix interpretation (Low–Moderate plausibility). However, Kul Tiras's explicit Celtic theme creates a severe design-aesthetic confound (Moderate–High). Key testable prediction: if *Ath-* is a genuine Drust morpheme, future *Ath-* names should appear only among Thornspeakers; if purely aesthetic, they should appear across all Kul Tiran characters.

---

## ru-skill: Round 84 — Release, endpoint, marketplace, parsing → Russian

One commit (129 insertions, 96 deletions, 20 files):

| Change | Scope |
|--------|-------|
| релиз → выпуск | Release terminology |
| эндпоинт → конечная точка | API terminology |
| маркетплейс → торговая площадка | Commerce terminology |
| парсинг → разбор | Processing terminology |
| ~30 replacements across ~20 files | Docs, workflows, skill docs, tests |

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
