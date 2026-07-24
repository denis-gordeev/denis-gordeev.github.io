---
title: "AUTOWORK - Seven repos July 24: otclick API v0.35.0 92.7% coverage and API key auth, divine-divinity 14 SystemParams clippy 46→28, wow rounds 84–87 HTML-MD sync and em-tag conversion, mcp-russia kontekst russification, ru-coverage round 88, ru-skill rounds 106–107, codex rounds 91–92"
date: 2026-07-24
layout: post
---

Seven monitored repos land new commits since July 23. **otclick** vaults from 87% to 92.74% coverage across four commits, adds API key authentication, self-hosted Manrope font, accessibility improvements, Literal-based breakdown validation, and reaches API v0.35.0. **open-divine-divinity-rust-bevy** introduces 14 new `SystemParam` structs across two commits (WorldEnvironment, CombatEvents, AutomapReadData, EnemyAiData, SaveWorldState, ReadingPanelData, PerformSaveInput, DragReleaseData, DialogInteractionData, DialogResponseData, SkillCombatData, ObjectInteractionData, NpcSkillDialogData, AreaDespawnData), reducing clippy warnings from 46 to 28. **wow_constructed_languages** completes rounds 84–87 fixing HTML-MD sync gaps across sethrak/dwarven/drust/darnassian/shalassian/zandali/pandaren/thalassian/vrykul/alien/titan-forged, plus converting 1046+ markdown `*text*` artifacts to proper `<em>` tags. **mcp-russia** russifies `context`→`kontekst` in middleware and `async context manager`→`асинхронный менеджер контекста`, plus fixes post-russification bugs in fssp and renames `_razobrat_fio` fields (lastName→familiya, firstName→imya, patronymic→otchestvo). **My-RU-Coverage** round 88 replaces `оператор перевозок`→`перевозчик`, `операторы хранения`→`организации хранения` across 16 occurrences and 14 reports, adds aliases in utils.py. **ru-skill** rounds 106–107 audit `API`→`программный интерфейс` in deep roadmap/TODO sections, `MVP`→`минимальный рабочий вариант`, `авторизация`→`проверка подлинности`, `логин`→`вход`, `CLI`→`интерфейс командной строки`, `Legacy-пакеты`→`Устаревшие пакеты`. **codex-console-english** rounds 91–92: scan clean, all 32 tests pass.

## otclick: API v0.35.0, 92.74% coverage, API key auth, accessibility (401 insertions, 20 files)

### Coverage 87%→92.74%, Dagster assets, version dedup

Adds cache eviction tests (expired entries, oldest eviction) and CSV export tests with non-empty rows — cache.py and csv_export.py both reach 100%. Deduplicates version string: api.py reads from importlib.metadata instead of hardcoded value; pyproject.toml is the single source of truth. Adds 7 Dagster asset tests via `build_asset_context`, fixes `DagsterFailure→Failure` bug in csv_backfill.py. Bumps coverage fail-under from 89%→92%. API version 0.31.0→0.34.0.

### API key auth, Literal breakdown, accessibility, self-hosted fonts

Adds backward-compatible API key authentication via `API_KEYS` env var (auth.py). Replaces breakdown field path parameter with `Literal` type for stricter validation. Adds `max_length` on package_name, country, lang query parameters. Self-hosts Manrope font via `@fontsource/manrope` (no Google Fonts CDN). Adds accessibility: form wrapper, `aria-labels`, `aria-disabled`, `role=row`. Adds ruff S (bandit) lint rules. Passes signal to `fetchWithTimeout` in exportCsv for cancellation. 5 new auth tests, 390 total pass, 92.74% coverage. API version → v0.35.0.

---

## open-divine-divinity-rust-bevy: 14 SystemParams, clippy 46→28 (938 insertions, 2 files)

### Commit 1 — WorldEnvironment, CombatEvents, AutomapReadData, EnemyAiData, SaveWorldState, ReadingPanelData

Introduces six `SystemParam` structs to reduce function parameter count and improve ergonomics. `WorldEnvironment` (time of day, weather, ambient settings), `CombatEvents` (event reader/writer for combat), `AutomapReadData` (automap state, discovered areas), `EnemyAiData` (AI state, patrol routes, aggro tables), `SaveWorldState` (save metadata, world state, checksum), `ReadingPanelData` (panel content, scroll position, font assets). Clippy warnings drop from 38 to 36.

### Commit 2 — PerformSaveInput, DragReleaseData, DialogInteractionData, DialogResponseData, SkillCombatData, ObjectInteractionData, NpcSkillDialogData, AreaDespawnData

Adds eight more `SystemParam` structs: `PerformSaveInput` (save slot, confirmation state), `DragReleaseData` (drag source, release target, drag state), `DialogInteractionData` (NPC, dialog tree, interaction state), `DialogResponseData` (player choice, NPC response text, reputation delta), `SkillCombatData` (skill cooldowns, combat log, combo state), `ObjectInteractionData` (interacted object, interaction type, loot table), `NpcSkillDialogData` (NPC skill, dialog trigger, skill level), `AreaDespawnData` (despawn timer, area, entities to despawn). Clippy warnings drop from 36 to 28.

---

## wow_constructed_languages: Rounds 84–87 — HTML-MD sync, em-tag conversion (645 insertions, 25 files)

### Round 84 — Sethrak, dwarven, drust, darnassian, shalassian, zandali, pandaren

Fixes sethrak dark theme / invisible headers / column placement, dwarven missing clause, drust missing Inferred/legend color. Updates darnassian, shalassian, zandali, pandaren anchor and CSS from prior round.

### Round 85 — Thalassian, vrykul, pandaren

Fixes thalassian bare asterisks / em tags / link / CSS, vrykul IPA headers / Drust links, pandaren link text.

### Round 86 — Darnassian, zandali, alien, titan-forged

Fixes darnassian grammar truncated text, zandali duplicate exclamations / CSS, alien and titan-forged stale refs and unconverted markdown.

### Round 87 — Comparative HTML em-tag conversion

Converts all `*text*` markdown artifacts to proper `<em>` tags in comparative HTML files — 1046+ instances across 5 files. Eliminates rendering inconsistencies where italics markup was being displayed as raw asterisks.

---

## mcp-russia: kontekst russification, fssp post-russification fixes (85 insertions, 5 files)

### context→kontekst, async context manager→асинхронный менеджер контекста

Renames `context`→`kontekst` parameter in server.py middleware (3 methods), updates all `context.message.name/uri`→`kontekst.message.name/uri`, `vyzvat_sleduyushchiy(context)`→`vyzvat_sleduyushchiy(kontekst)`. Replaces `async context manager`→`асинхронный менеджер контекста` in http_client.py.

### fssp post-russification bug fixes, _razobrat_fio russification

Fixes bugs from prior russification round in fssp module. Renames `_razobrat_fio` fields: `lastName`→`familiya`, `firstName`→`imya`, `patronymic`→`otchestvo`.

---

## My-RU-Coverage: Round 88 — оператор перевозок→перевозчик, операторы хранения→организации хранения (160 insertions, 22 files)

Replaces `оператор перевозок`→`перевозчик` and `операторы хранения`→`организации хранения` across 16 occurrences in 14 company reports (Akron, NLMK, Sber, X5, Magnit, Rosneft, Transneft, Nickel, SberAgro, MMK, Dom.RF, Lukoil, Surgutneftegas, Tatneft, Megapolis, Gazprom Neft). Adds aliases in utils.py for consistent terminology. Network graph data and index rebuilt.

---

## ru-skill: Rounds 106–107 — deep audit API→программный интерфейс, MVP, CLI (116 insertions, 9 files)

### Round 106

Replaces `API`→`программный интерфейс` in deep sections of roadmap/TODO, `MVP`→`минимальный рабочий вариант (MVP)`, `авторизация`→`проверка подлинности`, `логин`→`вход`.

### Round 107

Replaces 14 more `API`→`программный интерфейс` instances, `авторизация`→`проверка подлинности`, `логин`→`вход`, `лог-сообщения`→`сообщения журнала`, `Legacy-пакеты`→`Устаревшие пакеты`, `CLI`→`интерфейс командной строки`.

---

## codex-console-english: Rounds 91–92 — scan clean

Both rounds scan clean with all 32 tests passing. No translatable non-English content found.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
