---
title: "AUTOWORK - Five repos July 29: wow rounds 96-98 haranir/nerubian/7-dir sync and orcish/shath-yar audit, divine-divinity layout extraction 27 new tests, otclick v0.42→v0.45 Pydantic models and 98% coverage, mcp-russia russification and metadata, ru-skill round 112 jargon elimination"
date: 2026-07-29
layout: post
---

Five monitored repos land new commits since the previous round. **wow_constructed_languages** rounds 96–98 fix HTML-MD sync across haranir, nerubian, 7 more directories, and audit orcish/shath-yar with apostrophe normalization and CSS fixes. **open-divine-divinity-rust-bevy** extracts layout helpers (4958→3238 lines), adds 27 new tests (1117→1144), and nets -1848 lines. **otclick** advances from v0.42.0 to v0.45.0 with dead code removal, Depends() consolidation, Pydantic model extraction, and coverage up to 98%. **mcp-russia** russifies element→zapis (66 replacements), removes migration phrasing from docs, and updates public module metadata. **ru-skill** round 112 eliminates jargon reverts (эндпоинт, прокси, валидация, пагинация, ID, Topic ID).

## wow_constructed_languages: Rounds 96–98 — HTML-MD sync and orcish/shath-yar audit

### Round 96 — haranir and nerubian sync

Converts 367 markdown asterisk patterns, reorders sections, fixes broken anchors, corrects stale counts, and fixes an em tag in haranir and nerubian directories. 8 files changed.

### Round 97 — 7 directories: missing text, apostrophes, IPA wrapping

Fixes HTML-MD sync across earthen, eredun, ethereal, gutterspeak, kalimag, mogu, and qiraji. Addresses missing text, apostrophe normalization, section reorder, asterisk placement, IPA wrapping, and nav self-links. 14 files changed.

### Round 98 — orcish and shath-yar audit

Standardizes curly quotes/apostrophes to straight in orcish (53) and shath-yar (691) HTML files. Adds missing a:hover, h3, .shared, and .warning CSS classes. Fixes orcish grammar.md /sh/ → /ʃ/ in coda clusters, adds IPA span around /r/ in description, fixes h4 color in shath-yar grammar, and consolidates dual nav to single-nav pattern in shath-yar description. 8 files changed with 788 insertions and 763 deletions.

---

## open-divine-divinity-rust-bevy: Layout extraction, 27 new tests, net -1848 lines

Extracts layout helpers reducing game/layout.rs from 4958 to 3238 lines. Adds InteractiveObjectDef, QuestTrigger, and AreaTransition constructors. Extracts Plugin::build from 425 to 7 lines. Introduces WaveParams builder pattern. Combat module gains 79 lines, player_stats 75 lines. 27 new tests bring the total to 1144. Net reduction of 1848 lines across 6 files.

---

## otclick: v0.42.0→v0.45.0 — Pydantic models, 98% coverage

### v0.43.0 — Dead code removal, public health-check APIs

Removes dead code from api.py and es_search.py, adds public health-check API endpoints, cleans up test imports, adds cache_extra and es_search tests. 9 files changed.

### v0.44.0 — Depends() consolidation, httpx2, DAGSTER_HOME

Consolidates repeated query parameters (package_name, q, country, lang, min_stars) into ReviewFilters and DayFilter Depends() classes across 7 endpoints. Replaces httpx with httpx2 in dev deps, adds DAGSTER_HOME to .env.example, raises coverage fail-under from 93% to 95%. 5 files changed.

### v0.45.0 — Pydantic model extraction, 98% coverage

Moves 19 Pydantic models from api.py to play_reviews/models.py, reducing api.py from 768 to ~630 lines. Models.py coverage reaches 100%. Bumps coverage fail-under from 95% to 98%. 4 files changed.

---

## mcp-russia: Russification element→zapis, metadata updates

### element→zapis (66 replacements in 11 files)

Replaces `element` with `zapis` in loop variables across client.py and tools.py for 11 data modules. Removes migration phrasing from documentation: «не требует переноса»→«создаётся сразу», «переводите модуль»→«добавлении модуля». 15 files changed.

### Public module metadata

Updates public namespace metadata for fns, fssp, minobrnauki, roskomnadzor, rospotrebnadzor, and rosreestr modules. Adds test_public_namespace.py with 25 new assertions. 10 files changed.

---

## ru-skill: Round 112 — jargon revert elimination

Eliminates reverts of jargon terms: эндпоинт→конечная точка, прокси→посредник, отрендеренные→построенные, Legacy-обёртка→устаревшая обёртка, валидация→проверка, пагинация→постраничный вывод, ID→идентификатор, Topic ID→идентификатор темы. Updates regression tests across hh-vacancies, moex-shares, osm-nearby, postcalc-postcodes, stoloto-lotto, toss-securities, and yandex-market-search. 17 files changed.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
