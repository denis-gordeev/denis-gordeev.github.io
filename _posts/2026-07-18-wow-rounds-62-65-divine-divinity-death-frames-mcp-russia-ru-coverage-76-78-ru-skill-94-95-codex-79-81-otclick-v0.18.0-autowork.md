---
title: "AUTOWORK - WoW Rounds 62-65: Zandali serpent/venom register, HTML-MD sync across 13 directories; Divine Divinity death frames; mcp-russia round 82; ru-coverage rounds 76-78; ru-skill rounds 94-95; codex rounds 79-81; otclick security headers, 88+ new tests, API v0.18.0"
date: 2026-07-18
layout: post
---

Seven repositories see new commits on July 17–18: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships four rounds (62–65) with HTML-MD sync fixes across 13 directories and a new Zandali Pattern 19 serpent/venom register; **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds death frames and heuristic animation partitioning for enemies/NPCs; **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** completes round 82 with templates→shablony rename and РосАПИ key russification; **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships three rounds (76–78) replacing anglicisms, calques, and ~140 variable names; **[ru-skill](https://github.com/denis-gordeev/ru-skill)** eliminates jargon in rounds 94–95; **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** confirms full English compliance through rounds 79–81; and **[otclick](https://github.com/denis-gordeev/otclick)** lands five commits with 88+ new tests, security headers, Optional→X|None migration, and API v0.18.0.

## wow_constructed_languages: Rounds 62–65 (351 insertions, 30 files)

Four rounds continue the systematic HTML-MD synchronization and vocabulary expansion:

### Round 62: HTML-MD sync fixes across 6 directories

Fixes sync gaps in thalassian (kinship terms 'Not attested' → 'Confirmed'; vocabulary RPG table IPA column), shalassian (Tel'anor'ien → Tel'anor; missing corpus note), nerubian (broken table row, missing A'- morpheme, Rak- count 3→4, duplicate phonological pattern numbering), qiraji (vocabulary -ox row note, hieroglyphic writing bullet), orcish (duplicate Nagrand entry), and tol'vir (~20 missing details in grammar.html Investigations 2–4, NPC table column redistribution). 80 insertions across 12 files.

### Round 63: Gnomish/kalimag grammar sync, titan-forged comparative cross-references

Substantial HTML updates: gnomish grammar.html gains 77 lines of restored content, kalimag grammar.html gains 63 lines, and titan-forged-comparative.html receives 34 lines of updated cross-references linking to the ethereal/Shath'Yar content from earlier rounds. 159 insertions across 4 files.

### Round 64: Sethrak, mogu, pandaren, nerglish sync gaps

Fixes sethrak grammar.html nav links, restructures mogu vocabulary.md (66 lines rewritten), adds nerglish description.html entry, and corrects pandaren vocabulary sync issues in both .md and .html. 55 insertions across 6 files.

### Round 65: Zandali Pattern 19 (serpent/venom register), ethereal/nerubian sync

Adds Zandali Pattern 19 — a serpent/venom register distinction — to both grammar.md and grammar.html (17+20 lines). Also fixes ethereal grammar.html sync (5 lines), ethereal vocabulary.md, and nerubian grammar sync (vocabulary/grammar files). 57 insertions across 8 files.

---

## open-divine-divinity-rust-bevy: Death frames and animation partitioning (238 insertions, 4 files)

Adds `death_frames` field to `SpriteAnimation` with a `from_partitioned_frames()` constructor. Implements heuristic frame partitioning in `try_load_object_animation_frames()`: sprites with ≥8 frames are automatically split into 30/30/20/20 idle/walk/attack/death partitions. All 4 spawn sites updated to use `from_partitioned_frames` with death frames. 10 new tests bring the total from 946 → 956.

---

## mcp-russia: Round 82 — templates→shablony, РосАПИ key russification (278 insertions, 59 files)

Two commits advance the ongoing russification:

### templates→shablony, transliteration unification

Renames `templates/` → `shablony/` directory (7 template files moved), eliminates Portuguese artifact `formatirovat_data_extenso → formatirovat_datu_propisyu`, russifies keys (`city→gorod`, `param→parametr`, `msg→soobshcheniye`), and unifies transliteration (`osnovnoj→osnovnoy`, `subyekt→subiekt`, `obshhegosudarstvennye→obshchegosudarstvennye`). English tags in test_discovery.py also russified. 29 files changed.

### obiekt→obekt, instrument→imya_instrumenta, РосАПИ keys

Standardizes `obiekt → obekt` spelling across all modules, fixes `instrument → imya_instrumenta` in documentation (was ambiguous — could mean musical instrument), and russifies РосАПИ dictionary keys in `client.py` and `resources.py`. Updates 6 example docs and 6 regulatory data modules. 30 files changed.

---

## My-RU-Coverage: Rounds 76–78 (1,088 insertions, 30 files)

Three rounds continue the systematic anglicism and calque replacement:

### Round 76: 9 anglicisms in 7 files + 20 wikilink aliases

Replaces **капитальная дисциплина → контроль капитальных затрат** (IRAO), **дисциплины по рискам → контроля рисков** (BSPB), **Индустриальные клиенты → Промышленные клиенты** (HYDR), **Коммерческая модель → Модель деятельности** (CBOM), **подписочных услуг → услуг по подписке** (T), **подписочные лицензии → лицензии по подписке** (BAZA), **трендом → тенденцией**, **релевантным → подходящим, нерелевантные → неподходящие**. Adds 20 wikilink aliases in utils.py. 137 insertions across 12 files.

### Round 77: Calques + ~100 variable russifications + DIAS report

Replaces **бренд → торговая марка** (AFLT), **Контент-провайдеры → Поставщики контента** (YDEX). Russifies ~100 variables across 10 scripts. Adds DIAS (Диасофт) report achieving MOEXBMI 20/20 coverage. Audit reaches 43/43 (100%). 724 insertions across 21 files.

### Round 78: discover.py bug fix, ~40 variable russifications

Fixes a NameError bug in `discover.py`. Russifies ~40 variables including `parser/args → парсер/аргументы` across 11 scripts. Rebuilds graph_data.json. 227 insertions across 11 files.

---

## ru-skill: Rounds 94–95 (108 insertions, 24 files)

### Round 94: Residual jargon cleanup

Replaces **прокси-сервере → сервере-посреднике** (6), **через прокси → через посредника** (1), **endpoint → конечная точка** (4), **аутентификации → проверки подлинности** (2), **кэширует → буферизует** (1), **парсер → модуль разбора** (1). Updates skill-docs.test.js regression tests. 7 files.

### Round 95: Tautology and platform name cleanup

Eliminates **REST API** tautology, restores **push-уведомления** (was incorrectly shortened), replaces **macOS Keychain → Связка ключей**, **KakaoTalk Mac CLI → для Mac**, **Version Packages → Версии пакетов**. Updates roadmap.md with new entries. 17 files.

---

## codex-console-english: Rounds 79–81 (14 insertions, 3 files)

Three consecutive scans confirm the repository remains fully English with zero CJK/Cyrillic/non-translatable content. All 32 tests pass. Only TODO.md updates in each round.

---

## otclick: Five commits — 88+ new tests, security hardening, API v0.18.0 (2,126 insertions, 51 files)

The most active repo this round with five substantial commits:

### Unit tests for backend + analytics (e1d764e)

Adds 88 new tests: db.py (10 upsert query tests with preserve_on_null/COALESCE), csv_backfill.py (30 tests for header mapping, parsing, datetime handling), es.py (12 serialization and bulk action tests), queries.py (14 WHERE clause and comparison delta tests), useAnalytics.js (22 trend peak, anomaly detection, comparison card tests). 1,025 insertions across 6 files.

### Bug fixes and hardening (8bc047d)

Adds `conn.rollback()` in db_pool.py except block to prevent dirty transaction state on pooled connections. Fixes naive datetime UTC handling in es.py. Fixes SIGPIPE in smoke-check.sh under `set -euo pipefail`. Runs nginx as non-root in Dockerfile. Adds early return from `onMounted` when `loadApps()` fails. Fixes `.env.example` defaults (us/en → ru/ru). Simplifies `join_by_space()` and replaces hardcoded script list with glob. 73 insertions across 11 files.

### Search and breakdown composable tests (5cb6f63)

Adds 434 lines of tests: `useSearch.spec.js` (189 lines), `useBreakdown.spec.js` (181 lines), `SearchSection.spec.js` (64 lines). 458 insertions across 6 files.

### Optional→X|None, Promise.allSettled, query builder unification (b2ecdf7, API v0.17.0)

Replaces `Optional[X]` with `X | None` across api.py (64 occurrences). Switches `Promise.all` → `Promise.allSettled` for partial success in `refreshData()` and `loadAllBreakdowns()`. Adds `min_stars` URL hydration validation (1–5 range, integer check). Extracts `_buildFilterParams()` to unify query param builders. Adds `logger.warning` in 3 health endpoint except-blocks. 211 insertions across 7 files.

### Security headers, ES caching, retry UX (dbec21a, API v0.18.0)

Adds security headers to nginx (X-Frame-Options, X-Content-Type-Options, CSP, Referrer-Policy, Permissions-Policy), gzip compression, proxy timeouts, X-Forwarded-For/X-Forwarded-Proto. Caches Elasticsearch client in `es_search.py`. Adds `max_length=500` validation for `q` parameter (422 on oversized queries). Adds retry button to SummarySection.vue. 12 new component and API tests. 359 insertions across 10 files.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
