---
title: "AUTOWORK - WoW Rounds 44–50: Shalassian expansion, Dwarven investigations, Darnassian -dor cross-elven family, Nerubian sub-pattern typology, Hara'ni ancestry confirmation; Divine Divinity combat particles; mcp-russia constant russification; RU-Coverage round 70; ru-skill rounds 85–87 audit; codex-console round 74"
date: 2026-07-13
layout: post
---

Six repositories see new commits between July 9 and 13: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Rounds 44–50 with major Shalassian/Dwarven/Darnassian expansions, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds sprite particle integration in combat, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies constants and local variables, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** reaches round 70, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** completes rounds 85–87 with audit-driven fixes, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** verifies round 74.

## wow_constructed_languages: Rounds 44–50 — Major Shalassian/Dwarven/Darnassian expansions (4487 insertions, 50 files)

Seven rounds in four days, dominated by Shalassian and cross-elven analysis.

### Shalassian: Confirmed Phrases, Rath Paradigm, -dora Suffix (Rounds 45–47)

Round 45 is the largest single commit (2287 insertions). Five confirmed phrases and 25+ untranslated items are documented, alongside three new investigations. Round 46 adds Shalassian Investigations 4–6:

- **Rath paradigm**: *Rath* appears as a standalone word ("dark one") and as a suffix (*E'rath*, *Sed-rath*), suggesting a nominal root with prefixal modification.
- **-dora suffix**: *Erana-dora* confirmed translation "thousand-thanks" establishes *-dora* = "grace/thanks" as a distinct morphological form from *-dorah* = "honor."
- **Tor ilisar'thera'nal**: The iconic Nightborne farewell parsed as *Tor* (vocative?) + *ilisar* (plural?) + *thera* (see?) + *nal* (negation?).

Round 47 adds Shalassian Investigations 7–8 analyzing the greeting/farewell register and *E'rath* vs. standalone *Rath*.

### Dwarven: Six Confirmed Translations, -modan/-grim Cross-Family (Rounds 45–46)

Six confirmed Darnassian-to-Dwarven translations added, alongside three investigations:

- ***-modan / Modr***: *Ironforge* vs. *Dun Morogh* — *-modan* as "mountain" suffix paralleling Norse *-heim*, with *Modr* as possible cognate root.
- ***-grim***: Appears across Dwarf and Vrykul names (*Baelgrim*, *Grimnor*, *Grimtotem*). Cross-family element hypothesis vs. Norse aesthetic confound.

### Darnassian: -dor/-dora/-dorah Cross-Elven Morpheme Family (Round 50)

Investigation 18 traces the root *dor* "crown" across three suffixal outcomes:

| Form | Structure | Proposed Meaning | Attestations |
|------|-----------|-----------------|-------------|
| *-dor* | Root | Crown / base | *Teldrassil*, *Nordrassil*, *Amirdrassil*, *Arcan'dor* |
| *-dorah* | *dor* + *-ah* (nominalizer) | Honor / valor | *Anu Dorah*, *Thas'dorah*, *Shan'dorah* |
| *-dora* | *dor* + *-a* (adjectival/verbal) | Grace / thanks | *Anu'dora*, *Erana-dora* (Shalassian) |

The structural parallel between *Anu Dorah* (funerary) and *Anu'dora* (combat exclamation) — both *Anu* + *dor*-derived form — is the strongest cross-elven cognate evidence. Confidence Low–Moderate.

### Nerubian: Sub-Pattern Typology for Initial-Apostrophe Names (Round 50)

Four new names from memorial placards (*Kej'takaz*, *Xevex*, *Rak-Neraz*, *Izol*) expand the initial-apostrophe analysis. Sub-patterns identified: apostrophe as syllable boundary vs. morpheme boundary vs. phonological marker.

### Hara'ni: Ancestry Confirmation via Hagar (Round 49)

The *Curse of Ula'tek* campaign (patch 12.1.0) confirms Hara'ni ancestral stock, enabling re-evaluation of Hara'ni–Elven cognate confidence levels. Previously speculative connections can now be assessed against the confirmed ancestral framework.

### Under-Analyzed Languages: Eredun, Titan, Qiraji, Pandaren (Round 44)

Formal investigations added to four languages with minimal prior analysis: Eredun (3), Titan (3), Qiraji (2), Pandaren (1). Establishes baseline investigation structure for future vocabulary discoveries.

---

## open-divine-divinity-rust-bevy: Sprite particle integration and core combat systems (2 commits, 1251 insertions)

Two commits bring visual and gameplay improvements:

**Sprite particle effects in combat**: `spawn_particles_with_fallback()` tries sprite-sheet particles from `GameTextures` first, falls back to procedural colored squares. Wired into 5 combat systems (enemy AI, damage events, dragon breath, dragon dodge, dodge invincibility). All 20 particle spawn sites now use the fallback helper.

**Core combat system registration**: 5 previously unregistered combat systems (`update_enemy_ai`, `process_damage_events`, `handle_player_basic_attack`, `handle_enemy_deaths`, `handle_player_death`) now run in the Bevy Update schedule. `handle_player_death` fixed to use `Option<ResMut<PlayerDead>>` for the dynamically inserted resource. `handle_skill_hotkeys` remains unregistered due to Bevy 0.13's 16-parameter system limit (18 params).

**Earlier commit**: Automap scale adaptation for real world data, location tooltips, and sprite particle effect infrastructure.

---

## mcp-russia: Constant and variable russification (2 commits, 45 files)

Two commits continue the systematic replacement of English identifiers:

- **Constants**: `_ATTRIBUTION→_ISTOCHNIK`, `FIRES→POZHARY`, `MKB10_CLASSES→MKB10_KLASSY`, `CBR_DAILY_JSON→CBR_EZHEDNEVNYY_JSON`, `*_API_BASE→*_API_BAZA`, `*_URL→*_ADRES`, `DATA_GOV_RU→DANNYE_GOV_RU`, `BUDGET_GOV_RU→BYUDZHET_GOV_RU`, `OPEN_METEO→OTKRYTYY_METEO`, `CONSULTANT→KONSULTANT`, `MINZDRAV_OPEN_DATA→MINZDRAV_OTKRYTYE_DANNYE`, `DADATA_URL→DADATA_ADRES`; bugfix `region_dtp→subiekt_dtp`.
- **Local variables**: `_data→_dannye`, `_name→_nazvanie`, `_text→_tekst`, `_code→_kod`, `static→statika`, `_list→_spisok`; Pydantic field unification `_id→_identifikator`; bugfix `sud_name→nazvanie_suda`.

---

## My-RU-Coverage: Round 70 — Constants and parameters russified (1 commit, 10 files)

Round 70 replaces English identifiers across financial scripts:

- `SECTOR_THEME_MAP→СООТВЕТСТВИЕ_СЕКТОРОВ_ТЕМ`, `INDUSTRY_THEME_MAP→СООТВЕТСТВИЕ_ОТРАСЛЕЙ_ТЕМАМ`, `ISS_URL→АДРЕС_ISS`
- `dry_run→пробный_запуск` (13 occurrences across 3 scripts)
- `THEME_DEFINITIONS→ОПРЕДЕЛЕНИЯ_ТЕМ` in skill docs
- `витрины→площадки` in theme descriptions
- 42/42 (100%) quality reports pass; all 13 scripts compile without errors.

---

## ru-skill: Rounds 85–87 — Audit-driven fixes and jargon elimination (3 commits)

Three rounds continue the audit-based approach:

| Round | Key changes |
|-------|------------|
| 85 | трек→направление, CAPTCHA→проверка на робота, релиз→выпуск in historical records |
| 86 | Audit: Прокси→Посредник ×2, логина→входа ×2, эндпоинта→конечной точки ×1 — reverting jargon regressions |
| 87 | Audit: English table cells and jargon in brand-inventory, AGENTS.md; API identifiers wrapped in backticks |

---

## codex-console-english: Round 74 — Verified zero non-English content (1 commit)

Repository confirmed fully English. Zero CJK/Cyrillic/non-English characters in tracked source files. Non-ASCII limited to legitimate emojis, `Türkiye` in a test assertion, and `→` arrows in changelog notes. All 32 tests pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
