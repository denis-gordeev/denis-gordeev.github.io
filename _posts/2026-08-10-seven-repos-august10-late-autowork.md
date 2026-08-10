---
title: "AUTOWORK - Seven repos update: wow Rounds 112–114, mcp-russia 6 new Росстат tools + 256 total, divine-divinity 1306→1321 tests, otclick v0.57 + production hardening, ru-skill Round 121, ru-coverage Round 100, codex-console ~22 calque fixes"
date: 2026-08-10
layout: post
---

Seven monitored repositories have new commits since the earlier round today. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## wow_constructed_languages: Rounds 112–114 — corrupted headers, HTML-MD sync, 490+ em-dash fixes

**Round 112** fixes 7 more corrupted table headers, bare IPA dashes in drust and haranir, sethrak description/grammar/vocabulary sync with markdown source, and titan vocabulary updates. 8 files changed, 78 insertions, 61 deletions.

**Round 113** fixes HTML-MD sync issues: bare asterisks, missing CSS classes, IPA delimiters, and column mismatches in darnassian, nazja, orcish, thalassian, and vrykul vocabularies. 7 files changed, 27 insertions, 12 deletions.

**Round 114** performs a massive repository-wide pass: converts 335+ bare UTF-8 em dashes to `&mdash;` HTML entities across 46+ files, converts 100 bare dashes in IPA cells and 54 in non-IPA cells, adds 30 missing `<span class="ipa">` wrappers across 10 files, fixes a missing `</thead>` in nazja/vocabulary.html, and converts `*B-K-H*` markdown italics to `<em>` in nerubian grammar. 52 files changed, 594 insertions, 583 deletions.

---

## mcp-russia: 6 new Росстат tools, ФО russification, ЕМИСС contract tests — 27 modules, 256 tools

Major expansion of the Росстат module and continued codebase russification:

- **6 new Росстат tools**: `vvp_dannye` (GDP data), `bezrabotitsa_dannye` (unemployment), `dokhody_na_dushu` (per-capita income), `promyshlennoe_proizvodstvo` (industrial production), `uroven_bednosti` (poverty rate), `srednyaya_pensiya` (average pension). 154 new lines of tests.
- **ФО code russification**: Latin abbreviations replaced with Russian (ЦФО, СЗФО, ЮФО, СКФО, ПФО, УФО, СФО, ДФО) across 9 modules (МЧС, Минобрнауки, Минздрав, МВД, Роспотребнадзор, Россельхознадзор, Росстат, Ростехнадзор, kad_arbitrazh).
- **ЕМИСС contract tests**: Network contract tests for 14 ЕМИСС indicator codes (`MCP_RUSSIA_NETWORK_TESTS=1`).
- **Additional russification**: ГИБДД Tm/Tb → Тм/Тб; РосАПИ PATENT → PSN; Минздрав pharma/radio → farmatsevticheskaya/radiatsionnaya; fixed broken link adres_dannyeess → address.

The server now hosts **27 modules, 256 tools and resources**. All modules use Russian variable and function names, connected to real Russian government APIs.

---

## open-divine-divinity-rust-bevy: 9 functions → 18 helpers, 1306→1321 tests

Three refactoring commits extracting 18 helpers from 9 large functions:

**Commit 1** — Extract `process_damage_events`, `attempt_enchant`, `try_boss_special_attacks`, `handle_drag_release` into 9 helpers; 11 unit tests (1306→1317).

**Commit 2** — Extract `spawn_interactive_objects`, `handle_object_interaction`, `handle_skill_hotkeys` into 5 helpers; 4 combo tests (1317→1321).

**Commit 3** — Extract `validate_dialog_markers` (4 helpers, 135→54 lines) and `try_load_game_assets` (2 helpers); total 9 functions → 18 helpers across the refactoring round, 15 new tests (1306→1321).

---

## otclick: v0.57 + production hardening

Four consecutive commits advancing the review-analytics platform:

**v0.57.0**: Type annotations on DB and ES layers, middleware ASGI types, 108 new API tests, `DashboardHero` component test, `useApiFetch` test expansion. 12 files changed, 285 insertions, 20 deletions.

**Fix commit**: Narrowed bare `except Exception` in DB modules, added `focus-visible` CSS, Docker `HEALTHCHECK`, non-fatal `loadApps`, `useReviewsDashboard` composable test. 13 files changed, 112 insertions, 27 deletions.

**Feature commit**: Validated review days in dependencies, added 5 UI primitive component tests (`EmptyState`, `GlassCard`, `MetricCard`, `PillBadge`, `SectionHeader`). 10 files changed, 228 insertions, 5 deletions.

**Production hardening**: CORS configuration, rate limiting, Elasticsearch security script, E2E CI stage, security gates. 8 files changed, 109 insertions, 29 deletions.

---

## ru-skill: Round 121 — PR → запрос на слияние

Replaced 2 occurrences of English "PR" with Russian "запрос на слияние" in `docs/sources.md`. Audit confirms no previously fixed жаргонизмы have returned. Updated roadmap. 3 files changed, 23 insertions, 6 deletions.

---

## My-RU-Coverage: Round 100 — last English CLI flag

Replaced `--json` with `--джсон` across 2 scripts (6 occurrences) — the last remaining English CLI flag in the project. Updated `graph_data.json` accordingly. 5 files changed, 128 insertions, 118 deletions. Round 100 marks a milestone: all CLI flags in the project are now in Russian.

---

## codex-console-english: ~22 more Chinese-English calque fixes

Fixed approximately 22 Chinese-English calques and awkward phrasings across 20 files: `tool library` → `utility`, `paging` → `pagination`, `Maximum number of` → `Max`, `Failed to get` → `Failed to fetch/acquire`, and others in config, core utils, services, routes, and frontend JS. All 32 tests pass. 20 files changed, 63 insertions, 38 deletions.
