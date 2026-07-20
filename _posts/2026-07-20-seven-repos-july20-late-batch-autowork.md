---
title: "AUTOWORK - Seven repos July 20 late batch: otclick v0.23–0.26, divine-divinity system ordering, wow rounds 73–76, mcp-russia russification, ru-coverage round 83, ru-skill rounds 99–100"
date: 2026-07-20
layout: post
---

Seven monitored repos land new commits since the morning scan on July 20. **otclick** advances from v0.23.0 to v0.26.0 across four releases with CSV injection protection, thread-safe ES client, streaming export lifecycle fix, DB timeouts, and UI accessibility improvements. **open-divine-divinity-rust-bevy** adds system ordering constraints and a GameAssetData SystemParam. **wow_constructed_languages** completes rounds 73–76 with Nazja grammar expansion and HTML-MD sync fixes. **mcp-russia** continues russification of docs and CI/CD. **My-RU-Coverage** completes round 83. **ru-skill** reaches round 100. **codex-console-english** and **birdclef_2026** have TODO.md-only updates.

## otclick: v0.23.0–v0.26.0 — Four releases, hardening and accessibility (692 insertions, 29 files)

### v0.23.0 — CSV injection protection, container limits, ES 8.17.1

Adds `_sanitize_csv_cell` to prefix `=`, `+`, `-`, `@`, `\t`, `\r` with a single quote, preventing formula injection in CSV exports. Container resource limits (`mem_limit`, `cpus`) added to all docker-compose services. Elasticsearch image updated from 8.12.2 to 8.17.1. Two new CSV injection tests.

### v0.24.0 — Thread-safe ES client, middleware hardening, Redis resilience

`es_search.py` gains a `threading.Lock`-protected `_es_client()` for safe concurrent access. `api.py` logs ES exceptions via `logger.exception()`, and middleware catches `call_next` exceptions with logging before re-raise. `useApiFetch.js` forwards abort to timeout controller when `AbortSignal.any` is unavailable. `csv_export.py` converts `None` to empty string instead of literal `'None'`. `cache.py` catches `ImportError` when redis is missing but `REDIS_URL` is set, and deletes corrupted Redis keys on read. `useFilterPresets.js` validates preset structure from localStorage. Coverage raised from 60% to 75% (current: 77%). Version bumped to 0.24.0. Six new tests.

### v0.25.0 — Streaming export lifecycle, security, UI fixes

Critical fix: streaming CSV export `_db_connection()` context exited before the generator consumed it; now uses `_connect`/`_release_connection` in generator `finally`. Named cursor conflict resolved: hardcoded `'csv_export'` → `'csv_export_{uuid}'`. `rate_limit.py` warns about X-Forwarded-For trust when enabled. UI: `AnalyticsSection.vue` fixes SVG circle `cx=NaN` for single-point timeseries; `Btn.vue` adds `type='button'`; `useSearch.js` wraps 503 JSON parse in try/catch; `formatters.js` clamps `formatStars` to 0–5 range; `useReviewsDashboard.js` adds `loadApps()` signal support and popstate listener. API healthcheck added to `docker-compose.yml`. Version bumped to 0.25.0. Seven new tests.

### v0.26.0 — DB timeouts, ES reconnection, UI accessibility, useLocalRef

Adds `POSTGRES_CONNECT_TIMEOUT` (10s) and `POSTGRES_POOL_GETCONN_TIMEOUT` (30s) in `db_pool.py`. `_close_pool()` now calls `_pool.wait()` for proper drain. ES client gains `max_retries=3`, `retry_on_timeout=True`, and `_reset_es_client()` on search failure. Cache key prefix made configurable via `API_CACHE_KEY_PREFIX` env var. `fetchWithTimeout` validates `signal.aborted`. UI accessibility: `aria-pressed` on analytics horizon buttons, keyboard accessibility for SVG circles and recent-days divs. Extracts `useLocalRef` shared composable from `FiltersSection.vue` and `SearchSection.vue`. Fixes two failing CSV export tests. Fixes `pyproject.toml` build-backend for uv compatibility. Version bumped to 0.26.0. Nine new Python tests, four new UI tests.

---

## open-divine-divinity-rust-bevy: System ordering, PlayerDead fix, GameAssetData SystemParam (232 insertions, 3 files)

### System ordering constraints

Adds explicit `.after()`/`.before()`/`.chain()` ordering for hover→interaction, combat pipeline, animation sync→update, movement, day/night, weather, and HUD systems, eliminating nondeterministic execution order.

### PlayerDead event fix

Replaces `Commands::insert_resource` with `PlayerDeathEvent` to fix a 1-frame delay. `PlayerDead` becomes a persistent resource with a timer. Four new PlayerDead timer tests (986→990 total).

### GameAssetData SystemParam

Creates `GameAssetData` SystemParam consolidating 6 read-only asset resources. Applied to `spawn_game_world` (8→3 params), `update_asset_debug_panel` (13→9), `process_area_transition` (9→7), `process_area_transition_spawn` (15→10). Fix wasteful mutable claims: `update_enemy_ai`, `handle_player_basic_attack`, `sync_player_animation_state` now use immutable references. Clippy warnings: 49→48.

---

## wow_constructed_languages: Rounds 73–76 — Nazja grammar expansion, HTML-MD sync (351 insertions, 36 files)

### Round 73 — Darnassian, Thalassian, Nazja, Zandali

Fixes HTML-MD sync gaps in Darnassian and Thalassian. **Nazja grammar significantly expanded** in `nazja/grammar.html`. Zandali sync fixes. Completed TODO items cleaned up.

### Round 74 — Xal'atath, common, nerglish, vulpera

Adds Xal'atath to Shath'Yar Old God Names table. Fixes HTML-MD sync gaps in Common, Nerglish, and Vulpera vocabulary.

### Round 75 — Shath'Yar, Darnassian, Zandali, World Tree

Fixes HTML-MD sync gaps in Shath'Yar, Darnassian, and Zandali. Updates description World Tree translations across multiple language files.

### Round 76 — kalimag, sethrak, gutterspeak, orcish, vrykul, drust

Fixes HTML-MD sync gaps in Kalimag, Sethrak, Gutterspeak, Orcish, Vrykul, and Drust. Fixes Gutterspeak register count error.

---

## mcp-russia: Continued russification — IDs, docs, CI/CD, diagrams (201 insertions, 31 files)

### ID→Идентификатор and code russification

Renames `ID` → `Идентификатор` in `.gitignore`, `planner.py` examples, `CHANGELOG.md`, and `CONTRIBUTING.md`. Renames `as e` → `isklyuchenie` in code. Documentation files updated with `subiekty` parameter names. `cliff.toml`, CI/CD workflow steps, and diagrams russified. `adding-features.md` example updated. Image files renamed: `feature_anatomy.png` → `anatomiya_modulya.png`, `system_overview.png` → `obzor_sistemy.png`, `registry_flow.png` → `potok_avtoobnaruzheniya.png`, `data_flow.png` → `potok_dannykh.png`.

---

## My-RU-Coverage: Round 83 — Wikilink and docstring russification (177 insertions, 13 files)

### Latin wikilinks → Cyrillic (17)

17 remaining Latin wikilinks replaced with Cyrillic equivalents across pilot reports. Wikilink index updated in `WIKILINKS.md`. Network graph data refreshed.

### Terminology normalization

`потока посетителей` → `аудитория`, `пользовательская аудитория` → `аудитория пользователей` in reports. `CLI`, `stdout`, `JSON` replaced with Russian equivalents in docstrings. `utils.py` gains additional Russian identifiers. `moex_blue_chip_queue.py` and `moex_status.py` updated.

---

## ru-skill: Rounds 99–100 — URL, pagination, and authorization russification (98 insertions, 25 files)

### Round 99 — URL and pagination in zoon-nearby

Replaces `URL` → `адрес` and `пагинация` → `постраничная навигация` in zoon-nearby feature documentation.

### Round 100 — авторизация → проверка подлинности

Periodic audit revealed systematic use of "авторизация" as a synonym for the previously eliminated "аутентификация". Replaced with "проверка подлинности" across ~35 occurrences in 20 files for consistency with established terminology. Updates span SKILL.md files, README files, feature docs, install/setup docs, roadmap, and security documentation.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
