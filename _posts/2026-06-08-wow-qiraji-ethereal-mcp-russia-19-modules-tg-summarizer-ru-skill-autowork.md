---
title: "AUTOWORK - WoW Constructed Languages: Qiraji, Ethereal/Broker (29 languages); mcp-russia: all 19 modules live; tg_summarizer parallel NLP; ru-skill russification"
date: 2026-06-08
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository adds two more languages — Qiraji and Ethereal/Broker — bringing the total to 29 language folders, with deep morphological analyses of Aqir substrate morphemes and goblin name patterns. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** reaches a major milestone: **all 19 planned modules now have real government API integrations**, with rosvodresursy, minzdrav, and rosaudit connected in this round. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** gains intra-batch deduplication, parallel NLP checks, and input truncation. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** continues its comprehensive russification push across source code, workflows, and documentation.

## wow_constructed_languages: Qiraji and Ethereal/Broker, now 29 languages

Two new language entries extend the corpus to 29 folders with substantial morphological and onomastic analysis.

### Qiraji language and Aqir substrate (June 5)

A full **qiraji/** folder is created with vocabulary, grammar, description, and HTML vocabulary (with IPA). Key findings:

- **Ahn-** is identified as a shared Aqir substrate morpheme appearing in both Qiraji (*Ahn'qiraj*) and Nerubian (*Ahn'kahet*) — supporting the theory of a common Aqir linguistic ancestor
- **-naxx/-nax** geminate pattern: Qiraji retains geminates (Naxxramas, -naxx) while Nerubian simplifies them (Naxxanar → -nax)
- Six constructed Qiraji example sentences (Qr1–Qr6)
- Elder Nadox added to Nerubian vocabulary, extending the **-ox/-nax** suffix pattern
- Kobyss naming research added to Earthen vocabulary (no NPC names currently available)
- Titan-forged comparative table updated with Aqir substrate morpheme summary

### Ethereal/Broker language and Undermine goblin names (June 5)

An **ethereal/** folder is created based on TWW Ghosts of K'aresh campaign and TBC Netherstorm content:

- Potential **-esh/-aresh** locative suffix identified in *K'aresh* and *Tazavesh* (Low-Moderate confidence)
- Broker-Ethereal dialect hypothesis proposed — Brokers may represent a specialized register of the Ethereal language
- Six constructed example sentences (Et1–Et6)
- Undermine goblin names added to Gnomish vocabulary and HTML (Pamsy, Grimla Fizzlecrank, Nikki the Fixer, Gallywix, Gazlowe, Renzik, Revilgaz, Noggenfogger, Gallagio)
- Analysis of potential goblin morphemes: **-gaz/Gaz-**, **-wix/-ik**, **-gio**
- Gnomish morpheme analysis expanded with the new data

## mcp-russia: all 19 modules now have real APIs

Two commits bring mcp-russia to a significant milestone — every planned Russian government data module now connects to a real API.

### Four more real APIs — Минобрнауки, Роспотребнадзор, Роскомнадзор, Росстат (June 5)

- **Минобрнауки** (obrnadzor.gov.ru): education oversight data
- **Роспотребнадзор** (proverki.rospotrebnadzor.ru): consumer rights and sanitation inspections
- **Роскомнадзор** (rkn.gov.ru): communications oversight
- **Росстат** (fedstat.ru): federal statistics

Stale links cleaned up. Running count: **16/19 modules with real APIs**.

### Final three — rosvodresursy, minzdrav, rosaudit — complete the set (June 5)

- **rosvodresursy**: State Water Register (text.water.ru) and ГМВО (gmvo.skniigkh.ru)
- **minzdrav**: ФРМО (frrr.rosminzdrav.ru), Росздравнадзор (roszdravnadzor.gov.ru), open data (data.minzdrav.gov.ru)
- **rosaudit**: Счётная палата (ach.gov.ru) and budget.gov.ru

Mixed-script code fix (antiкоррупция → antikorruptsiya). Remaining Portuguese text cleaned from cliff.toml and test files. **1974 tests passed, 1 skipped.**

**mcp-russia now has 19/19 modules with real government API integrations.**

## tg_summarizer: dedup, parallel NLP, input truncation

Two commits improve the summarization pipeline:

### Summary temperature and deterministic edits (June 5)

- Summary generation temperature set to 0.3 for more deterministic output
- Deterministic update edit generation
- Code deduplication in summary handling

### Intra-batch dedup, parallel NLP, cache fix (June 5)

- Fixed `load_group_summaries_history` not caching empty results (previously every call re-read the file)
- Added `_remove_intra_batch_duplicates`: SequenceMatcher-based dedup before sending to summary LLM
- Added `SUMMARY_MAX_INPUT_CHARS_PER_MESSAGE` (3000): truncate long messages before summary generation
- Added `NLP_CONCURRENT_CHECKS` (5): parallel NLP classification with `asyncio.Semaphore`
- Extracted `_save_summary_to_history_file` shared helper
- Removed dead `_classify_message` method (inlined into `process_messages`)
- **13 new tests (125 total, up from 112)**

## ru-skill: comprehensive russification

Four commits continue the systematic russification of all user-facing surfaces:

- **Source code error messages, CHANGELOG headings, and API response values** russified; doc-regression suite expanded
- **Repo-governance surfaces** russified; remaining mixed-language drift closed
- **GitHub Actions workflow files** russified; automatic CHANGELOG heading translation via `fix-changelog-headings.js`; doc-regression expanded
- **Shell helper statuses** russified (June 6)

## My-RU-Coverage: acronym russification

- Expansion of B2B/B2C/POS acronyms into Russian
- Canonical Russian wiki-links for BaaS, DRaaS, фулфилмент, IaaS
- Typo fix «сегент» → «сегмент» in AFKS
- BaaS/DRaaS added to WIKILINK_ALIASES

## codex-console-english: minor fix

- Database tab casing fix

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
