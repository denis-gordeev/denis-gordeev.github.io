---
title: "AUTOWORK - Seven repos July 19 late batch: otclick v0.21–0.22, divine-divinity directional sprites, wow rounds 66–72, mcp-russia round 85, ru-coverage rounds 79–81, ru-skill rounds 96–98, codex-console rounds 82–84"
date: 2026-07-19
layout: post
---

Seven monitored repos land new commits on July 19. **otclick** advances to v0.22.0 with full OpenAPI error documentation, shellcheck-clean bootstrap, and 29 new tests. **open-divine-divinity-rust-bevy** adds directional sprite frame selection and registers 31 previously dormant game systems. **wow_constructed_languages** completes rounds 66–72 with a deep HTML-MD sync audit. **mcp-russia** continues russification (round 85). **My-RU-Coverage** completes rounds 79–81. **ru-skill** runs rounds 96–98. **codex-console-english** scans rounds 82–84.

## otclick: v0.21.0 — Full non-2xx OpenAPI docs, bootstrap script, Makefile (5 commits, 633 insertions)

### OpenAPI error responses for all endpoints

v0.21.0 adds `ErrorResponse` and `HealthResponse` schemas to OpenAPI for every non-2xx response: health 503, rate-limit 429 on all endpoints, search 503, breakdown 422. The `_error_responses()` helper now accepts multiple status codes, and `_ERROR_RESPONSE_DESCRIPTIONS` gains a 429 entry. Every endpoint documents its possible error codes.

### Bootstrap and Makefile

`scripts/setup-dwh-venv.sh` replaces the old `setup-dwh.sh` with a shellcheck-clean implementation. `dwh/Makefile` adds `bootstrap`, `test`, `lint`, `clean`, `dev`, and `api` targets. `dwh/requirements-dev.txt` gains `ruff` and `pytest-cov`. `dwh/pyproject.toml` adds coverage configuration and updates dev dependencies.

### v0.22.0 — Bug fixes and 29 new tests

Fixes Vue prop mutations in `FiltersSection.vue` and `SearchSection.vue` (local refs + emit instead of v-model), re-enables `vue/no-mutating-props` ESLint rule. Fixes `_InProcessCache.set()` ignoring per-entry TTL. Fixes `rate_limit.py: get_remote_address()` called without request arg. Adds `RATE_LIMIT_STORAGE_URI` to `docker-compose.yml`. 29 new tests: config (6), rate_limit (11), logging_config (5), es_search (7), cache TTL (2), FiltersSection emits (2).

---

## open-divine-divinity-rust-bevy: Directional sprites, 31 registered systems (441 insertions)

### Directional sprite frame selection

Adds `DirectionalFrameSet` with per-direction frame vectors for all 8 `FacingDirection` values. `SpriteAnimation` gains optional `directional_idle/walk/attack/death` fields. `current_frames()` checks directional frames first, falling back to base frames. Horizontal flip is skipped when directional frames are in use. Merges `BossEncounterState` into `CombatMusicState` (removing the standalone resource). 14 new tests (972 → 986 total).

### Register 31 unregistered systems

All 31 Bevy system functions that were defined but never added to the `GamePlugin` Update schedule are now registered, including critical systems: `update_camera_to_follow_player`, `handle_object_interaction`, `handle_dialog_interaction`, `spawn_enemies_once`, `update_health_bars`, `update_day_night_cycle`, `update_skill_bar`, and more. Consolidates `handle_object_interaction` params (17 → 16) by merging `object_query` + `object_anim_query`. Removes dead stubs `deposit_item_to_home` and `withdraw_item_from_home`.

---

## wow_constructed_languages: Rounds 66–72 — Deep HTML-MD sync audit (373 insertions, 31 files)

Seven rounds of cross-referencing HTML and Markdown sources across all language directories. Rounds 66–69 audit Shath'Yar cross-references, Haranir grammar (`/h/` gradient note), Taur-ahe grammar, and add Common Midnight vocabulary. Rounds 70–72 fix sync gaps in Nature, Titan, Draenei, Drust, Dwarven, and Darnassian; update the elven-comparative wordlist; add a `*-well*` fount convention to README. The autowork.log is trimmed (77k lines removed). A `.gitignore` is added.

---

## mcp-russia: Round 85 — Continued russification (182 insertions, 22 files)

Round 85 renames `_MAP` → `_SLOVAR`, `mkb_classes` → `mkb_klassy`, `klass_css` → `klass_stiley` across documentation and code. Additional russifications: `region` → `subiekt_rf`, `exc` → `isklyuchenie`, `status` → `sostoyanie`. Documentation files (`adding-features.md`, `features.md`, example docs) updated with Russian parameter names.

---

## My-RU-Coverage: Rounds 79–81 — Anglicism cleanup (219 insertions, 18 files)

Round 79: штаб-квартира → главный офис, SGA → УКР, CAPEX/FCF → Russian terms in comments, `yfinance` → источник данных, `dict` → словарь in docstring. Round 80: клиентская база → базы клиентов, Nautilus → Наутилус, hybrid identifier cleanup, report counter fixes. Round 81: штаб-квартира → главный офис, Astra Linux → Астра Линукс, Linux → Линукс, HPE/RHEL simplification, 14 new aliases. Network graph and financial scripts updated accordingly.

---

## ru-skill: Rounds 96–98 — Interface documentation russification (220 insertions, 42 files)

Round 96: ботов → роботов, пагинация → постраничная навигация, SSR explanation, formatting. Round 97: послеустановочные, оформление заказа на сайте, публично доступный сайт. Round 98: URL → адрес, ID → идентификатор, hybrid term cleanup in interface documentation. Updates across SKILL.md files, README files, and feature docs.

---

## codex-console-english: Rounds 82–84 — Full English scan (20 insertions, 3 files)

Round 82: no changes needed, repository fully English. Round 83: fixes 2 Chinese-English calque artifacts — "the number of" and "Authorization Code". Round 84: full English scan, no translatable content found, all 32 tests pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
