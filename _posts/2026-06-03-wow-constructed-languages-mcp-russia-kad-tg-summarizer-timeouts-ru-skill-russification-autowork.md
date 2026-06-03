---
title: "AUTOWORK - WoW Constructed Languages: 17 conlangs with IPA and comparative linguistics, mcp-russia КАД API, tg_summarizer timeout hardening, ru-skill russification, My-RU-Coverage legacy terms"
date: 2026-06-03
layout: post
---

A new **wow_constructed_languages** repository debuts with grammars, vocabulary, and IPA transcriptions for 17 World of Warcraft constructed languages, including comparative elven linguistics and Proto-Elven reconstruction. **mcp-russia** connects the Court Arbitration (КАД) API and russifies the redator module. **tg_summarizer** adds OpenAI timeout handling, NLP truncation, and fetch limits. **ru-skill** continues English→Russian heading and metadata translation on the feat/mchs-storm-warnings branch. **My-RU-Coverage** cleans up 27 semiconductor and 13 material legacy terms, adds MOEX company tickers, and fixes wikilink aliases.

## wow_constructed_languages: 17 conlangs from Azeroth

A brand-new **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository catalogs the constructed languages of World of Warcraft. Three commits in a single day built it from scratch into a comprehensive linguistic resource.

### Initial 11 languages

The first commit establishes grammars and descriptions for 11 languages: Darnassian, Thalassian, Draenei, Orcish, Zandali, Taur-ahe, Dwarven, Shath'Yar, Kalimag, Shalassian, and Gutterspeak. Each folder contains `vocabulary.md` (attested canon words with source notes), `grammar.md` (inferred rules from observed examples), and `description.md` (cultural context and attestation reliability).

### IPA transcriptions and comparative linguistics

The second commit adds HTML vocabulary files with IPA phonetic transcriptions for Darnassian, Thalassian, and Orcish, plus three new languages: Pandaren, Vulpera, and Eredun/Demonic. The standout deliverable is **elven-comparative.html** — a cross-reference of Darnassian, Thalassian, and Shalassian with cognate sets, sound correspondences, and Proto-Elven reconstruction. Constructed example sentences (clearly marked non-canon) demonstrate inferred grammar for six languages.

### Six more languages and expanded vocabularies

The third commit adds IPA/HTML vocab for seven more languages, a Draenei/Eredun comparative analysis, and three additional languages: Mogu, Sethrak, and Nature/Druidic (a vocabulary compilation, not a distinct language). Pandaren and Mogu cross-references link contact vocabulary from millennia of domination.

The repo now covers **17 language entries** across a spectrum from moderate attestation (Darnassian, ~30-35 items) to extremely low (Vulpera, Sethrak — proper names only). The methodology is strict: attestation first, no invented words, and all inferences clearly labeled.

## mcp-russia: Госдума, Закупки, and КАД APIs

Two commits on **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** connect three more real data sources:

- **Госдума API** (api.duma.gov.ru): deputies, bills, and votes, authenticated with `DUMA_API_TOKEN`
- **Закупки API** (zakupki.gov.ru): procurement search, contracts, and plans, with cross-module ФНС integration
- **КАД API** (kad.arbitr.ru): court arbitration cases

The redator module was russified, and documentation was cleaned up. mcp-russia now has **7 modules with real API connections** (ЦБ РФ, Росгидромет, ФНС, Госдума, Закупки, КАД, Open-Meteo) out of approximately 20 planned.

## tg_summarizer: timeout and truncation hardening

Two more commits on the **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** `autowork/2026-04-08-lambda-hardening` branch:

- **Cache invalidation fixes**: `text_hash` extracted to shared utils, defensive `SummaryInfo` handling, cost optimization, and code deduplication
- **Timeout and truncation**: OpenAI request timeout, NLP text truncation before processing, configurable fetch limit for message batches, and Telegram connect timeout — all aimed at preventing Lambda timeouts

## ru-skill: continued russification on feat/mchs-storm-warnings

Four commits on **[ru-skill](https://github.com/denis-gordeev/ru-skill)** continue the English→Russian translation sweep:

- **English surfaces → Russian**: Boundary note → Граничное примечание, SKILL.md h1 headings, package READMEs, frontmatter descriptions
- **Legacy boundary copy russification**: remaining English boundary text replaced
- **Transition copy and metadata alignment**: package metadata aligned with new Russian surfaces
- **Changeset summaries and SKILL.md frontmatter**: russified, doc-regression tests expanded

## My-RU-Coverage: legacy term cleanup and MOEX tickers

Two commits on **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)**:

- **Anglicism annotations**: Russian explanations for 12 anglicisms at first mention (пост-трейдинговые→послеторговые, хаб→узловой аэропорт, кейс→инвестиционная логика, etc.), script russification across 4 files
- **Legacy term purge**: 27 semiconductor TECH_TERMS and 13 MATERIAL_TERMS cleaned up, WIKILINK_ALIASES fix (Газпром нефть→GAZP), `LOCAL_COMPANY_TICKERS` dict added (MOEX and other exchanges → local_company), `discover.py` sectors aligned with actual folders, stale `.claude/skills/` references removed

## codex-console-english: rounds 23–24

Rounds 23 and 24 of the translation verification scan: all 29 tests pass, no non-English text found. The codebase remains clean.

## russia-md: upstream review

A June 2 commit on **[russia-md](https://github.com/denis-gordeev/russia-md)** reviews upstream/main at `7d2b0fef9` — no additional applicable fixes beyond what was already synced.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
