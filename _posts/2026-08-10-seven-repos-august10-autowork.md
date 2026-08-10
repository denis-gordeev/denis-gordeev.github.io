---
title: "AUTOWORK - Seven repos update: wow Rounds 109–111, mcp-russia dinamika_regiona + 27 modules, divine-divinity 1278→1306 tests, otclick v0.54–v0.56, ru-skill Round 120, ru-coverage Round 99, codex-console Round 105"
date: 2026-08-10
layout: post
---

Seven monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## wow_constructed_languages: Rounds 109–111 — IPA consistency, HTML header/IPA wrapper fixes

**Round 109** performs repository-wide IPA consistency pass: replaces bare `—` delimiters with proper IPA span wrappers, adds missing `<span class="ipa">` wrappers, and removes markdown artifacts across darnassian, drust, earthen, ethereal, gnomish, haranir, kalimag, nazja, pandaren, shath-yar, taur-ahe, thalassian, titan, tolvir, vrykul, zandali, and common directories. 42 files changed, 498 insertions, 466 deletions.

**Round 110** fixes corrupted HTML headers, false IPA wrappers, and markdown artifacts in common, darnassian, drust, earthen, gnomish, haranir, nerubian, orcish, qiraji, shath-yar, and zandali. 22 files changed, 329 insertions, 317 deletions.

**Round 111** continues cleanup: fixes corrupted headers, broken links, spurious tags, false and missing IPA wrappers across alien-comparative, darnassian, elven-comparative, eredun-draenei-comparative, ethereal, gnomish, haranir, kalimag, nazja, nerubian, qiraji, shath-yar, taur-ahe, titan-forged-comparative, tolvir, and zandali. 24 files changed, 202 insertions, 192 deletions.

---

## mcp-russia: dinamika_regiona tool, ЕМИСС code updates, 27 modules / 250 tools

Major updates to the Росстат module and documentation:

- **dinamika_regiona**: New tool providing chronological series of a regional indicator with year filtering and rate-of-change calculation. 61 new lines of tests.
- **sravnenie_okrugov**: New tool for rating and comparing federal districts by a selected indicator.
- **ЕМИСС codes**: Updated 27 indicator codes after the Росстат transition to ОКВЭД 2; refreshed constants.py (136 lines reorganized).
- **Documentation sync**: Fixed metadata desynchronization across CONTRIBUTING.md, README.md, development guide, and features.md; corrected module count and tool descriptions.

The server now hosts **27 modules, 250 tools, 87 resources, 59 prompts**. All modules use Russian variable and function names, connected to real Russian government APIs.

---

## open-divine-divinity-rust-bevy: Spawn/equipment/dialog refactoring, 1278→1306 tests

Two major refactoring commits extracting 22 helpers from 8 large functions:

**Commit 1** — Spawn and scene setup refactoring (10 helpers extracted from `spawn_area_enemies`, `respawn_enemies_from_save`, `spawn_boss_hazards`, `setup_scene`); 14 new unit tests (1278→1292).

**Commit 2** — Equipment, skill minigame, dialog, and map helpers (12 helpers extracted from `handle_equipment`, `update_skill_minigame_panel`, `handle_dialog_response_keys`, `spawn_placeholder_map`):
- Equipment: `find_first_equippable_index`, `equip_slot_name`, `unequip_first_occupied_slot`
- Minigame panels: `format_lockpicking_panel`, `format_pickpocketing_panel`, `format_bartering_panel`
- Dialog: `apply_dialog_reputation_effects`, `claim_dialog_reward`, `apply_learned_skill`, `advance_dialog_quest_triggers`
- Map: `build_tile_sprite_bundle`, `build_overlay_sprite_bundle`

14 new unit tests (1292→1306). 2 files changed, 965 insertions, 698 deletions.

---

## otclick: v0.54.0 – v0.56.0

Three consecutive releases:

**v0.54.0**: Preserved the Elasticsearch error boundary — narrowed `except Exception` to `(ApiError, TransportError)` so unexpected app errors no longer silently reset the ES client. Added test for `RuntimeError` non-reset behavior. 6 files changed.

**v0.55.0**: ES proxy hardening with `limit_req_zone` (30 r/s per IP, burst 20, 429 on excess), `client_max_body_size 1m`, access/error logging. Playwright E2E smoke tests (3 tests: page load, search input, API health). CI deploy stage added. 11 files changed, 206 insertions, 8 deletions.

**v0.56.0**: JSON parse safety in `useBreakdown.js` (try/catch matching `_parseJsonResponse` pattern). Lazy config for `RATE_LIMIT_STORAGE_URI`. Alembic `autocommit=True` for DDL safety. CSP `font-src 'self'` for self-hosted Manrope font. Narrowed ES exception handling. CI: `pip-audit` now scans API requirements; `ui-e2e` job enabled for feature-branch MRs. i18n: table headers translated to Russian. SQL injection warning comment in `queries.py`. 12 files changed, 84 insertions, 19 deletions.

---

## ru-skill: Round 120 — English h1 and missing abbreviations

Fixed English h1 heading in `hwp/SKILL.md`. Added missing SSR/CSR abbreviation expansions in `zoon-nearby` and `yandex-market-search` SKILL.md descriptions. Updated roadmap. 6 files changed, 33 insertions, 10 deletions.

---

## My-RU-Coverage: Round 99 — russification

Replaced «интернет-» with «онлайн-» (10 occurrences, 5 reports), «интеграционные» with «по интеграции» (2), «рабочая нагрузка» with «вычислительная задача» (DATA), «облачные поставщики» with «поставщики облачных услуг» (3), «инфраструктура перевозок» with «транспортно-складская» (2). Fixed i/j → и/ж in `build_network.py` (8 occurrences). Added 11 aliases in `utils.py`. 15 files changed, 167 insertions, 138 deletions.

---

## codex-console-english: Rounds 104–105

**Round 104**: Scan clean — all 32 tests pass, no translatable non-English content found.

**Round 105**: Fixed Chinese-English calques and awkward phrasings across 8 files (config, core register, email/settings/websocket routes, email_services.js, settings.js). 8 files changed, 23 insertions, 15 deletions.
