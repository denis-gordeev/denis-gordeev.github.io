---
title: "AUTOWORK - WoW Investigations 30-32: -athir cognate and untranslated phrase analysis, Divine Divinity difficulty HUD + music, MCP-Russia constant russification, RU-Coverage round 63, ru-skill round 80 hybrid term unification, tg_summarizer token optimization, codex-console round 66"
date: 2026-07-06
layout: post
---

Seven repositories see new commits on July 6: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Investigations 30-32 with -athir cognate analysis and systematic untranslated phrase decoding, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds area difficulty HUD, scaled boss phases, and background music (827 tests), **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies remaining English constants and variables, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships round 63 with taxonomic and financial terminology cleanup, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 80 with ~100 hybrid term unifications across ~50 files, **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** reduces UPDATE_SUMMARY_MAX_TOKENS 2000→1000 and expands meta-artifact stripping (620 tests), and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** verifies all tracked files English-only in round 66.

## wow_constructed_languages: Investigations 30-32 — -athir cognate, untranslated phrase analysis, Shath'Yar attestation fix

Three commits (642 insertions, 66 deletions, 21 files):

### Investigation 30: -athir cognate, /h/ gradient analysis, daldorah compound

- **-athir** identified as a shared Proto-Troll-Elven morpheme meaning "memory/remnant": Hara'ni *Har'athir* ("remembered one") ↔ Darnassian *Alathir*, *Kal'methir*, *Lemor'athra* (three Nazjatar spire names)
- **/h/ distribution gradient** across five elven-family languages documented: Hara'ni ~20% > Nazja ~4% > Darnassian <1% > Thalassian/Shalassian 0% — exactly as predicted by progressive /h/ → ∅ sound change (confidence upgraded to **Moderate**)
- **daldorah** compound analyzed: *dal* "fortune" + *dorah* "valor/honor" (*-ah* nominalizer on *dor* "crown")

### Investigation 31: Third dorah attestation, -athir/-athra alternation, cross-family -thir

- **Third Darnassian dorah attestation**: *Thara dormil dorah* (Priestess of Elune) — all three Darnassian *dorah* attestations occur in sacred/ritual contexts, strengthening *dor* → *dorah* pair
- **-athir/-athra vowel alternation**: four hypotheses tested (case marking, number, phonological conditioning, different morpheme) — none confirmed; **Low–Moderate** confidence
- **Cross-family -thir distribution**: Hara'ni/Darnassian *-athir*, nerubian *Krik'thir*, Shath'Yar *K'thir* — assessed as independent /θ/-heavy aesthetic convergence (**Very Low–Low** confidence for cross-family connection)
- **Hara'ni Hagar ↔ Nazja Haghazed**: shared /h-ɡ/ onset in authority-figure names noted as testable prediction (**Very Low** confidence)

### Investigation 32: Systematic untranslated phrase analysis, Shath'Yar attestation fix 56+→87+

- **33 untranslated Darnassian phrases** systematically decoded by known-morpheme extraction:
  - **6 highly decodable** (2+ known morphemes): e.g., *Ishnu-talah Kaldorei* = "Blessings [of] death, Children of the Stars" (**Moderate**); *Zin-al-Elune!* = "Glory of Elune's light!" (**Moderate–High**)
  - **14 moderately decodable** (1 known morpheme): including five phrases advancing the *ther-* "battle/beware" root — *therador* in *Anu therador mali* potentially = "battle-crown" compound
  - **Advancing Investigation 12**: *Enu thora'serador* may contain a third *-ndV*-family form (*Enu* alongside *Andu*/*Endu*)
- **Shath'Yar attestation count** corrected from 56+ to 87+ (systematic re-audit)
- Investigation count: 12 → 16

---

## open-divine-divinity-rust-bevy: Area difficulty HUD, boss phases, background music

One commit (742 insertions, 16 deletions, 6 files):

- **Area difficulty HUD indicator** in automap header with color-coded tier display (5 difficulty tiers across 10 areas)
- **Difficulty-scaled boss phase health thresholds**: Safe tier delays phase transitions, Extreme accelerates them
- **Background music system**: 12 area/combat/menu tracks loaded from CMP archive, with combat-specific track switching
- 13 new tests (814 → 827 total)

---

## mcp-russia: Remaining English constant and variable russification

One commit (47 insertions, 20 deletions, 4 files):

- **TEMPLATES_DIR → DIREKTORIYA_SHABLONOV**, **NORMAS_DIR → DIREKTORIYA_NORM**
- **filepath → put_fayla**, **_DIGITS_RE → _RE_TSIFR**, **uri → adres_uri**
- Continuing systematic russification of remaining English identifiers

---

## My-RU-Coverage: Round 63 — Taxonomic and financial terminology cleanup

One commit (119 insertions, 104 deletions, 9 files):

| Change | Scope |
|--------|-------|
| Тарантол → Тарантул | Correct spelling |
| Ядро\|YADRO → Ядро | Latin alias removal |
| бизнеса → деятельности | Business terminology |
| сегментирована → разделена | Plain-language replacement |
| Маржинальность → Маржа | Financial terminology |

---

## ru-skill: Round 80 — Hybrid term unification ENGLISH-русское → русское ENGLISH

One commit (~100 replacements across ~50 files):

Systematic reordering of ~35 hybrid compound patterns from English-first to Russian-first, following Russian noun-adjective word order:

| Before | After |
|--------|-------|
| API-ключ | ключ API |
| JSON-ответ | ответ JSON |
| HTML-страницы | страницы HTML |
| MCP-сервер | сервер MCP |
| DOM-парсер | программа разбора DOM |
| SSR-страницы | страницы с серверной отрисовкой (SSR) |

Regression tests updated.

---

## tg_summarizer: Token reduction, meta-artifact expansion

One commit (259 insertions, 8 deletions, 8 files):

- **UPDATE_SUMMARY_MAX_TOKENS reduced from 2000 to 1000** — update prompts only insert a link, so 1000 tokens (~2000 chars) is sufficient; cost optimization
- **12 new filler patterns** added to `strip_meta_artifacts`: *ясное дело, стало быть, по большому счёту, так или иначе, между тем, тем временем, как правило, ввиду этого, в силу этого, надо сказать, следует понимать*
- 26 new tests (594 → 620 total)

---

## codex-console-english: Round 66 — English-only verification

One commit (12 insertions, 5 deletions, TODO-only):

- All tracked files verified English-only — zero CJK or Cyrillic characters
- Repository remains translation-complete; no new artifacts found

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
