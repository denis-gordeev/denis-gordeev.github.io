---
title: "AUTOWORK - Seven repos July 23: ru-coverage round 87 main→главный, otclick API v0.31.0 87% coverage, divine-divinity SystemParams, mcp-russia _razobrat_sostoyanie, ru-skill round 105, wow rounds 81–83, codex round 90"
date: 2026-07-23
layout: post
---

Seven monitored repos land new commits since July 22. **My-RU-Coverage** completes round 87, replacing `main()`→`главный()` across 12 scripts, `as f`→`as ф`, `tag`→`тег`, and translating MOEX keys before report construction. **otclick** reaches API v0.31.0 with 87% overall coverage, api.py at 100%, dead code removal, and expanded README. **open-divine-divinity-rust-bevy** introduces 6 new `SystemParam` structs (DialogContextData, CameraViewData, FactionQueryData, LoadAssetData, TrapQueryData, CompanionExplorationData) plus DialogChoiceEntry, reducing clippy warnings from 46 to 38. **mcp-russia** russifies `_VyboryTableParser`→`_RazborshchikTablitsVyborov`, `_razobrat_status`→`_razobrat_sostoyanie`, `info_api`→`svedeniya_ob_api`, and `call_next`→`vyzvat_sleduyushchiy`. **ru-skill** reaches round 105 with hardened `fix-changelog-headings.js` error handling, russified k-skill-proxy startup message, and HH API→программный интерфейс HH audit. **wow_constructed_languages** completes rounds 81–83 fixing HTML-MD sync gaps across 6 language families and normalizing CSS theme across all vocabulary.html files. **codex-console-english** round 90 replaces an em dash in settings.html placeholder.

## My-RU-Coverage: Round 87 — main→главный, MOEX key translation (159 insertions, 15 files)

### Function and variable russification

Replaces `main()` → `главный()` across 12 scripts (add_ticker, audit_ru_reports, build_network, build_themes, build_wikilink_index, discover, generate_moex_reports, moex_blue_chip_queue, moex_status, update_enrichment, update_financials, update_valuation). Replaces `as f` → `as ф` in discover.py, `tag` → `тег` in build_themes.py. Moves MOEX key translation before report construction in moex_blue_chip_queue.py for consistent Cyrillic output. Network graph data and index rebuilt.

---

## otclick: API v0.31.0, 87% coverage, dead code removal (196 insertions, 5 files)

### api.py 100% coverage, dead code removal

Removes unreachable `es_not_configured` branch from `search_reviews` (Elasticsearch check is already handled upstream). Adds 146 lines of API tests for complete api.py coverage. Overall coverage rises from 85% to 87%. API version bumps to v0.31.0.

### README overhaul

Expands README with full endpoint documentation (health, apps, reviews, search, breakdown, timeseries, period-compare, CSV export), common query parameters, structured error envelope description, and testing instructions (`pytest`, `make test`, `make lint`, `make check`). Changes default country/lang examples from `us`/`en` to `ru`/`ru`.

---

## open-divine-divinity-rust-bevy: 6 SystemParams, DialogChoiceEntry, clippy 46→38 (294 insertions, 2 files)

### SystemParam consolidation

Introduces six new `SystemParam` structs to reduce function parameter count: `DialogContextData` (interaction state, character stats, day/night cycle, claimed rewards), `CameraViewData` (window and camera queries), `FactionQueryData` (faction lock, chest, reputations), `LoadAssetData` (asset source, archives, sprite packs, world data, object catalog, textures, state, server), `TrapQueryData` (poison gas, collapsing floor, timed escape), `CompanionExplorationData` (current area, discovered areas, puzzle state, faction reputations). Adds `DialogChoiceEntry` struct for dialog choices with line index, response text, NPC text, condition, reputation delta, and reward. Refactors `try_load_game_assets` to use `LoadAssetData`. Clippy warnings drop from 46 to 38.

---

## mcp-russia: Identifier russification, .env.example update (99 insertions, 15 files)

### _VyboryTableParser→_RazborshchikTablitsVyborov, _razobrat_status→_razobrat_sostoyanie

Renames `_VyboryTableParser` → `_RazborshchikTablitsVyborov` in cekrf/client.py with all references updated. Renames `_razobrat_status` → `_razobrat_sostoyanie` and `karta_statusov` → `karta_sostoyaniy` in fns/client.py (status→состояние semantic alignment). Renames `info_api` → `svedeniya_ob_api` in cekrf/resources.py and server.py (resource URI updated to `data://svedeniya-ob-api`). Replaces `call_next` → `vyzvat_sleduyushchiy` in server.py middleware. Updates `.env.example` `code_mode` → `rezhim_koda`. All 681 tests pass.

---

## ru-skill: Round 105 — error handling, proxy startup russification, HH API audit (136 insertions, 7 files)

### fix-changelog-headings.js hardened

Adds directory existence check, `try/catch` around file read/write, `withFileTypes` filtering, and Russian status messages (`"Каталог пакетов не найден"`, `"Не удалось прочитать"`, `"Заголовки CHANGELOG русифицированы"`). Adds idempotency regression test.

### k-skill-proxy startup message russified

`console.error(error)` → `console.error("Не удалось запустить сервер-посредник:", error.message)` in server.js. Regression test added.

### HH API audit

Replaces 2 remaining `HH API` instances → `программного интерфейса HH` / `программному интерфейсу HH` in hh-vacancies/SKILL.md. Roadmap updated with round 105 status. 11 key jargon terms audited; remaining `API` occurrences are in proper names only.

---

## wow_constructed_languages: Rounds 81–83 — HTML-MD sync, CSS normalization (499 insertions, 40 files)

### Round 81 — Zandali, Shath'Yar sync gaps

Fixes HTML-MD sync gaps in Zandali Investigations 9/12/13 and Shath'Yar vocabulary.

### Round 82 — Common, Orcish, Nerglish, Vulpera sync gaps

Fixes Common asterisk artifacts and truncated cells, Orcish broken IPA, Nerglish missing sentence, Vulpera unconverted markdown and spurious labels.

### Round 83 — CSS theme normalization

Normalizes CSS theme across all vocabulary.html files (darnassian, draenei, drust, dwarven, earthen, eredun, ethereal, gnomish, gutterspeak, haranir, kalimag, mogu, nature, nazja, nerglish, nerubian, orcish, pandaren, qiraji, sethrak, shath-yar, taur-ahe, thalassian, titan, tolvir, vrykul, vulpera, zandali). Fixes titles, nav elements, and content formatting gaps.

---

## codex-console-english: Round 90 — em dash replacement (4 insertions, 2 files)

Replaces em dash in `settings.html` placeholder text. TODO.md updated with round status. All tests pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
