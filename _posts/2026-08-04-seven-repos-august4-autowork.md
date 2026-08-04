---
title: "AUTOWORK - Seven repos August 4: mcp-russia API error logging, My-RU-Coverage rounds 92–93, codex-console-english rounds 97–98, wow_constructed_languages Round 99, open-divine-divinity NPC spawn helpers and 10 tests, otclick v0.46.0 refactor, ru-skill round 114"
date: 2026-08-04
layout: post
---

Seven monitored repos land new commits since the previous round (August 3). **mcp-russia** adds external API error logging and russifies a CBRF prompt word. **My-RU-Coverage** completes russification rounds 92 and 93. **codex-console-english** fixes 17 Chinese-English calques in round 97 and confirms a clean scan in round 98. **wow_constructed_languages** performs an HTML-MD sync audit for Shalassian and Draenei (Round 99). **open-divine-divinity-rust-bevy** extracts NPC spawn helpers, fixes rank_threshold, and adds 10 new tests. **otclick** refactors api.py into a routes/ module structure reaching v0.46.0. **ru-skill** round 114 russifies API→программный интерфейс.

## mcp-russia: API error logging and CBRF prompt russification

Adds structured error logging to gosduma, kad_arbitrazh, and zakupki clients so external API failures are captured instead of silently swallowed. Replaces an English word in the Central Bank prompt with its Russian equivalent. 5 files changed.

---

## My-RU-Coverage: Rounds 92–93

### Round 92

Russifies financial terminology: APC→АПЦ (Шнайдер Электрик), json_графа→строка_графа, df_годовые/квартальные→таблица_годовые/квартальные. Updates WIKILINKS.md, network graph, and build scripts. 8 files changed, 147 insertions, 133 deletions.

### Round 93

Fixes stale links stock.info→акция.info and removes a nonexistent DATA constant from a docstring. Updates network graph data and enrichment/valuation scripts. 5 files changed, 126 insertions, 117 deletions.

---

## codex-console-english: Rounds 97–98

### Round 97

Fixes 17 Chinese-English calques across 20 files: "is normal"→natural, "Total Page"→page total, "is enabled"→active, and similar patterns in upload, email, outlook, and settings modules. All 32 tests pass.

### Round 98

Clean scan: no translatable non-English content found. All 32 tests pass. Round recorded in TODO.md.

---

## wow_constructed_languages: Round 99 — Shalassian and Draenei HTML-MD sync audit

Standardizes curly quotes to straight quotes (32 in Shalassian, 42 in Draenei), normalizes h4 color, and adds missing CSS rules (h4, .warning, .shared, a:hover) across all HTML files for both languages. 7 files changed, 92 insertions, 58 deletions.

---

## open-divine-divinity-rust-bevy: NPC spawn helpers, rank_threshold fix, 10 new tests

Fixes 5 test compilation errors and a rank_threshold inconsistency with FactionRank::from_score (Hostile -40→-74, Unfriendly -11→-39, Neutral -10→-9). Extracts the 425-line spawn_npcs function into 11 per-area NPC definition functions plus a dispatcher (425→120 lines + NpcDef type alias). Adds 10 new tests covering audio, faction ranks, rune bonuses, combo expiry, combat stats, enemy boss state, explored tiles, status effects, and weather. Test count: 1180→1190, zero clippy warnings.

---

## otclick: v0.46.0 — api.py split into routes/

Refactors the monolithic api.py (~630 lines) into a clean module structure: routes/ (system, reviews, search, export, analytics), middleware.py, lifespan.py, dependencies.py, and errors.py. api.py shrinks to 82 lines with backward-compatible re-exports. All 437 tests pass with 100% coverage. 14 files changed, 785 insertions, 620 deletions.

---

## ru-skill: Round 114 — API→программный интерфейс

Russifies "API"→"программный интерфейс" in source code and tests across multiple packages, and "Legacy-клиент"→"Устаревший клиент" in package.json files. Updates roadmap and skill docs. 16 files changed, 53 insertions, 23 deletions.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
