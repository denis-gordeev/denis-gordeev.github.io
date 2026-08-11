---
title: "AUTOWORK - Seven repos update: wow Round 115, mcp-russia 257 tools + poisk_regiona + resources/prompts, divine-divinity 1321→1343 tests, otclick security baseline, ru-skill Round 122, ru-coverage Round 101, codex-console Round 107"
date: 2026-08-11
layout: post
---

Seven monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## wow_constructed_languages: Round 115 — bare IPA wrappers, double nav merges

Round 115 fixes 47 bare IPA wrappers and 1 bare em dash across 19 language directories (alien-comparative, darnassian, elven-comparative, ethereal, gnomish, haranir, kalimag, nerubian, shalassian, taur-ahe, titan-forged-comparative, tolvir, zandali), and merges 5 double `<nav>` blocks in shalassian and taur-ahe description/grammar/vocabulary pages. 20 files changed, 46 insertions, 59 deletions.

---

## mcp-russia: poisk_regiona, weighted aggregation, resources and prompts — 27 modules, 257 tools

Major Росстат module expansion with new tools, resources, prompts, and dead code removal:

- **poisk_regiona**: New tool for searching Russian federal subjects by substring match.
- **Weighted aggregation**: `sravnenie_okrugov` now uses population-weighted aggregation for relative indicators (using NASELENIE_SUBIEKTOV reference).
- **3 new resources**: `data://pokazateli` (indicators), `data://okved` (economic activity codes), `data://subiekty-rf` (federal subjects).
- **3 new prompts**: `analiz_vrp_regionov` (GRP analysis), `obzor_truda` (labor overview), `analiz_demografii` (demographics analysis).
- **Dead code removal**: Deleted unused `poluchit_indikator`, `_razobrat_otvet_indikatora`, `PokazatelRosstata`.
- **Demografiya enhancement**: Added "Ест. прирост" (natural growth) column; `InflyatsiyaDannye` and `DemografiyaDannye` schemas now used in client.

The server now hosts **27 modules, 257 tools, 90 resources, 62 prompts**. All modules use Russian variable and function names, connected to real Russian government APIs.

---

## open-divine-divinity-rust-bevy: 12 helpers extracted from 8 functions, 1321→1343 tests

Continued refactoring streak — 12 new helpers extracted from 8 large functions, 22 new unit tests:

- `spawn_hud_bar` + `HudBarParams` from `spawn_player_hud_bars` (132→~20 lines)
- `resolve_npc_dialog_tree` + `build_npc_sprite_bundle` from `spawn_npcs` (130→~55)
- `spawn_catacombs_traps` / `spawn_black_ring_fortress_traps` / `spawn_castle_stormfist_traps` from `spawn_trap_elements_in_area` (137→~12)
- `assemble_choice_groups` from `build_dialog_tree_from_text` (147→104)
- `spawn_automap_grid_children` from `resize_automap_on_area_change` (135→~55)
- `can_enchant_recipe` / `format_enchanting_recipe_line` / `format_enchantable_items` from `update_enchanting_panel` (126→~50)
- `compute_merchant_discount` / `compute_buy_price` / `compute_sell_price` from `update_merchant_panel`
- `skill_unavailable_reason` + `cursor_world_position` from `handle_skill_hotkeys` (197→183)

2 files changed, 825 insertions, 484 deletions.

---

## otclick: Bandit B608 baseline, npm audit fix, Prettier formatting

Security baseline and formatting cleanup:

- **Bandit B608 baseline**: Added `[tool.bandit] skips = ["B608"]` to `dwh/pyproject.toml` — B608 (SQL injection) false positives on parameterized queries via `%s` placeholders; aligned with `ruff ignore = ["S608"]`. Bandit now reports 0 findings at `-ll`.
- **npm audit fix**: Updated 16 packages — eliminated 6 HIGH vulnerabilities (brace-expansion, esbuild, nanoid, picomatch, postcss, rollup, vite, yaml); `npm audit --audit-level=high` now 0 findings.
- **Prettier formatting**: Formatted 5 pre-existing files (AnalyticsSection spec, PeriodComparisonSection spec, FiltersSection, ReviewsTableSection, Btn).
- All checks pass: ruff (0 errors), pytest (476 passed, 100% coverage), vitest (247 passed), eslint (0 errors), shellcheck (0 errors), bandit (0 findings), npm audit (0 vulnerabilities), prettier (0 issues).

9 files changed, 484 insertions, 377 deletions.

---

## ru-skill: Round 122 — жаргонизм return elimination

Round 122 eliminates the return of previously fixed жаргонизмы in deeper sections of TODO.md, docs/roadmap.md, and changeset:

- **TODO.md**: 11 replacements — CLI, валидация, Open PR, аккаунт, Overpass API, free/no-key, Legacy, PR, backlog → Russian equivalents.
- **docs/roadmap.md**: CLI → интерфейс командной строки (CLI) (1 replacement).
- **.changeset/osm-nearby-add.md**: Overpass API → программный интерфейс Overpass (1 replacement).
- **scripts/skill-docs.test.js**: Updated round counter to 122.

4 files changed, 37 insertions, 21 deletions.

---

## My-RU-Coverage: Round 101 — Интернет→Онлайн

Replaced «Интернет-канал» with «Онлайн-канал» (APTK) and «Интернет-клиенты» with «Онлайн-клиенты» (MGNT). Updated graph data and added 2 aliases in `utils.py`. 6 files changed, 125 insertions, 114 deletions.

---

## codex-console-english: Round 107 — Failed to get → Failed to obtain

Replaced "Failed to get" with "Failed to obtain" in `register.py` (9 occurrences). Updated TODO.md. 2 files changed, 20 insertions, 10 deletions.
