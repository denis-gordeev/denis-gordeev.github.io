---
title: "AUTOWORK - Seven repos update: wow Rounds 116-118, mcp-russia metadata refresh, divine-divinity 1343→1359 tests, otclick refresh race + ES hardening, ru-skill Round 123, ru-coverage Round 102, codex-console Round 108"
date: 2026-08-11
layout: post
---

Seven monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## wow_constructed_languages: Rounds 116–118 — table headers, markdown asterisks, IPA wrappers

Three rounds of HTML quality improvements across 33 files:

- **Round 116**: Fixed 4 corrupted table headers, 4 missing CSS rules, and 81 bare Unicode arrows across 21 files.
- **Round 117**: Fixed 430+ markdown asterisks in inferred/uncertain spans and bare Unicode entities across 22 HTML files.
- **Round 118**: Wrapped ~50 bare IPA phoneme references in comparative HTML files with `span.ipa` tags.

33 files changed, 700 insertions, 673 deletions.

---

## mcp-russia: Metadata refresh — counters, ADR links, Portuguese cleanup

Housekeeping commit aligning documentation with current state:

- **README.md**: Updated tool count 256→257, client modules 24→26.
- **settings.py**: Corrected tool count from `257+` to exact `257`.
- **server.py**: Replaced ADR-001/002 references with CONTRIBUTING.md link.
- **CHANGELOG.md**: Removed Portuguese originals with diacritics; Russian translations preserved.
- **TODO.md**: Consolidated completed tasks, round 114.

5 files changed, 23 insertions, 35 deletions.

---

## open-divine-divinity-rust-bevy: 8 more functions extracted into helpers, 1343→1359 tests

Continued refactoring — 8 large functions decomposed, 16 new unit tests:

- `create_unique_item` → `build_unique_item` (126→~30 lines)
- `update_character_stats_panel` → `reputation_label`, `format_attributes_text`, `format_skills_text`, `format_inventory_section` (121→~30)
- `spawn_skill_bar` → `spawn_skill_bar_slot` (116→~30)
- `handle_puzzle_interaction` → `handle_lever_interaction`, `handle_keyslot_interaction` (117→~30)
- `update_location_marker_tooltips` → `find_closest_location_marker` (124→~75)
- `handle_crafting_input` → `attempt_craft_recipe` (119→~30)
- `update_rune_combo_panel` → `rune_slot_selector`, `format_rune_fusion_preview`, `format_rune_combinations_list`, `format_rune_fusion_lines` (115→~15)
- `handle_dialog_response_keys` → `navigate_dialog_to_node`, `close_dialog` (123→~75)

2 files changed, 783 insertions, 515 deletions.

---

## otclick: Stale refresh race fix, URL validation, meaningful E2E, ES hardening

Two significant commits improving reliability and security:

- **Stale dashboard refresh race**: `refreshData()` now binds completion to a specific `AbortController` — an aborted previous refresh no longer clears `loading` or overwrites error state for the active request. Competitive Vitest test added.
- **URL hydration hardening**: `day` accepts only valid `YYYY-MM-DD` dates not in the future; `offset` normalizes to safe integers aligned to `PAGE_SIZE`. Parameterized regression tests for impossible/future dates and fractional/unaligned offsets.
- **E2E smoke improvements**: Added same-origin `/api/health` endpoint in UI nginx; Playwright now applies a text filter and verifies URL synchronization, and health check requires exact `200` + `status: ok`.
- **ES exception narrowing**: Replaced `except Exception` + `isinstance` pattern with direct `except (ApiError, TransportError)` in `_es_search()`.
- **Logging idempotency guard**: `_logging_initialized` flag prevents double root logger configuration.
- **DSN caching**: `_POSTGRES_DSN` read once from env at init; `_dsn()` returns cached value.
- **Parametrized ES version**: Both `docker-compose.yml` files now use `${ELASTIC_VERSION:-8.17.1}`.

13 files changed, 195 insertions, 20 deletions.

---

## ru-skill: Round 123 — Overpass API in link texts, OIDC clarification, dotenv-file

Audit round eliminating remaining hybrid terms:

- **Overpass API in link texts**: 3 occurrences in `packages/osm-nearby/SKILL.md`, `packages/osm-nearby/README.md`, `docs/features/osm-nearby.md` → Russian equivalents.
- **OIDC without Russian explanation**: 3 occurrences in `AGENTS.md` and `docs/releasing.md` → added «открытая идентификация» clarification.
- **dotenv-файл**: 1 hybrid term in `scripts/check-setup.sh` → pure Russian equivalent.

9 files changed, 26 insertions, 27 deletions.

---

## My-RU-Coverage: Round 102 — интернет→онлайн, kwargs→именованные_аргументы, corporate terminology

Continued russification of financial and technical terms:

- интернет-платформа→онлайн-платформа (7), интернет-реклама→онлайн-реклама (2)
- инвесторские отношения→отношения с инвесторами (2), годовая→годовой отчёт (2)
- `**kwargs`→`**именованные_аргументы`
- контур обслуживания→система обслуживания (4)
- оператор сферы→организатор торгов (MOEX)
- Grammar fix for AFKS

24 files changed, 220 insertions, 151 deletions.

---

## codex-console-english: Round 108 — scan clean

Full scan found no translatable non-English content. All 32 tests pass.
