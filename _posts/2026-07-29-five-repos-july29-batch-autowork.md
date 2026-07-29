---
title: "AUTOWORK - Five repos July 29: wow rounds 96–98 HTML-MD sync across 10 directories, divine-divinity layout extraction and 27 new tests, otclick v0.43–v0.45 Pydantic models and httpx2, mcp-russia element→zapis russification, ru-skill round 112 jargon reverts"
date: 2026-07-29
layout: post
---

Five monitored repos land new commits since the previous round. **wow_constructed_languages** completes rounds 96–98 with HTML-MD sync fixes spanning 10 language directories. **open-divine-divinity-rust-bevy** extracts layout helpers (4958→3238 lines), adds 27 new tests (1117→1144), and introduces constructors and builder patterns. **otclick** progresses from v0.43.0 to v0.45.0 with dead code removal, Depends() consolidation, httpx2 migration, and Pydantic model extraction. **mcp-russia** russifies element→zapis and refreshes public module metadata. **ru-skill** round 112 eliminates jargon reverts (эндпоинт, прокси, валидация, пагинация).

## wow_constructed_languages: Rounds 96–98 — HTML-MD sync across 10 directories

### Round 96 — haranir, nerubian sync (367 asterisk conversions)

Fixes 367 markdown asterisk conversions in nerubian, reorders sections, repairs broken anchors, updates stale counts, and corrects em tag formatting. 8 files changed across haranir and nerubian directories.

### Round 97 — 7 directories (missing text, apostrophes, IPA, nav self-links)

Fixes missing text, normalizes apostrophes, corrects asterisk placement and IPA wrapping, removes nav self-links across 7 directories including mogu, qiraji, and others. 14 files changed with 125 insertions and 108 deletions.

### Round 98 — orcish and shath-yar audit

Standardizes curly quotes/apostrophes to straight in orcish (53) and shath-yar (691) HTML files. Adds missing CSS classes (a:hover, h3, .shared, .warning). Fixes /sh/→/ʃ/ in orcish coda clusters, wraps IPA in shath-yar description, corrects h4 color, and consolidates shath-yar dual-nav to single-nav pattern. 28 files changed with 1116 insertions and 1070 deletions across three rounds.

---

## open-divine-divinity-rust-bevy: Layout helper extraction, 27 new tests (1117→1144)

Extracts layout helper from game.rs (4958→3238 lines), reducing the module by 1720 lines. Introduces `InteractiveObjectDef`, `QuestTrigger`, and `AreaTransition` constructors. Extracts `Plugin::build` (425→7 lines) and introduces `WaveParams` builder pattern. 27 new tests added. Net reduction of 1848 lines across 6 files. Combat module grows with new helper functions.

---

## otclick: v0.43.0→v0.45.0 — dead code removal, Depends() consolidation, Pydantic model extraction

### v0.43.0 — dead code removal, public health-check APIs, test import cleanup

Removes dead code, exposes public health-check API endpoints, and cleans up test imports. 9 files changed.

### v0.44.0 — Depends() consolidation, httpx2, DAGSTER_HOME, coverage 95%

Consolidates repeated query params (package_name, q, country, lang, min_stars) into `ReviewFilters` and `DayFilter` Depends() classes across 7 endpoints. Replaces httpx with httpx2 in dev deps, eliminating StarletteDeprecationWarning. Adds DAGSTER_HOME to .env.example. Raises coverage fail-under from 93% to 95%.

### v0.45.0 — Pydantic models extraction, coverage 98%

Moves 19 Pydantic models from api.py to play_reviews/models.py, reducing api.py from 768 to ~630 lines. Models.py coverage: 100%. Bumps coverage fail-under from 95% to 98%. API version 0.44.0→0.45.0. 12 files changed with 367 insertions and 249 deletions across all three versions.

---

## mcp-russia: element→zapis russification, metadata refresh

Replaces element→zapis across 66 occurrences in 11 files (loop variables in client.py/tools.py). Removes migration-era phrasing from documentation (ofitsialnyy-redaktor.md, adding-features.md, ekonomist.md). Refreshes public module metadata. 24 files changed with 180 insertions and 130 deletions.

---

## ru-skill: Round 112 — jargon revert elimination

Eliminates reverted jargon terms: эндпоинт, прокси, отрендеренные, Legacy-обёртка, валидация, пагинация, ID, Topic ID. Updates regression tests and skill documentation. 17 files changed.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
