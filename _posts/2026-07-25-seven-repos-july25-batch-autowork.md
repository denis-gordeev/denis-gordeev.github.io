---
title: "AUTOWORK - Seven repos July 25: otclick API v0.38.0 93% coverage CORS and error envelopes, divine-divinity 15 SystemParams clippy 28→0, wow rounds 88–90 Naigtal and Vanguard, mcp-russia migration cleanup, ru-coverage round 89, ru-skill round 108, codex rounds 92–93"
date: 2026-07-25
layout: post
---

Seven monitored repos land new commits since the previous round. **otclick** advances from API v0.35.0 to v0.38.0 across three commits: lazy auth/CORS init, App.vue ref unwrap, rate_limit wraps fix, coverage jumps to 93% with api.py/db_pool.py/es_search.py reaching 100%, then adds CORS lazy init, auth 401 and rate-limit 429 error envelopes, es_search lifespan init. **open-divine-divinity-rust-bevy** introduces 15 new `SystemParam` structs (CombatMusicData, CharacterStatsPanelData, LocationTooltipData, CompanionRecruitData, DragonBreathData, AutomapResizeData, AutomapUpdateData, LocationMarkerUpdateData, AssetDebugData, EnemyDeathData, SkillMinigameInputData, PlayerAttackData, DamageProcessData, PuzzleInteractionData, DragonDodgeData) plus type aliases, eliminating all clippy warnings (28→0). **wow_constructed_languages** completes rounds 88–90: updates Naigtal/Dimensius entries and adds The Vanguard faction, fixes HTML-MD sync across 7 directories (ethereal, mogu, kalimag, gutterspeak, earthen, qiraji, shalassian), and resolves orcish IPA inconsistency and alien-comparative link text. **mcp-russia** removes migration artifacts: renames CI workflow НИК→Непрерывная интеграция, License attribution to mcp-russia участники, rewords docs to remove migration language, russifies variable `o`→`obrashcheniye`, adds examples table to index. **My-RU-Coverage** round 89 eliminates calques ИТ-решения→ИТ-продукты, ИТ-стек→ИТ-компоненты, fixes stale ФСФР URL (fsfm.ru→e-disclosure.ru). **ru-skill** round 108 removes reverted anglicisms CLI→интерфейс командной строки, парсинг→разбор, legacy→устаревший. **codex-console-english** rounds 92–93 scan clean.

## otclick: API v0.36.0→v0.38.0, 93% coverage, CORS/auth/rate-limit error envelopes (260 insertions, 12 files)

### v0.36.0 — App.vue ref unwrap, auth lazy init, rate_limit wraps fix

Refactors App.vue to properly unwrap Vue refs (removes stale `.value` access). Adds lazy initialization for auth module (API_KEYS read on first request instead of import time). Fixes `rate_limit` decorator wrapping order and `resources.py` defaults. Adds 30 new API tests. Removes unused docker-compose service definition.

### v0.37.0 — Coverage 93%, api.py/db_pool.py/es_search.py 100%

Adds 23 db_pool extra tests (connection reuse, pool exhaustion, error propagation) and 28 es_search tests (lifespan init, query building, error handling). Adds 12 more API edge-case tests. Coverage rises from 92.74%→93%, with api.py, db_pool.py, and es_search.py each hitting 100%.

### v0.38.0 — CORS lazy init, auth 401 error envelope, rate-limit 429 error envelope, es_search lifespan init

Adds lazy CORS middleware initialization (first-request setup instead of import time). Returns auth failures as structured JSON 401 error envelope. Returns rate-limit rejections as structured JSON 429 error envelope. Initializes Elasticsearch search within the FastAPI lifespan context. 38 new tests covering error envelopes and lifespan. Total 390+ tests pass.

---

## open-divine-divinity-rust-bevy: 15 SystemParams, type aliases, clippy 28→0 (830 insertions, 5 files)

Adds 15 new `SystemParam` structs plus 4 type aliases to reduce function parameter counts and improve ergonomics across game.rs and audio_playback.rs:

- `CombatMusicData` — time, player/enemy transforms, area, music assets/state, combat music state, music/fade queries
- `CharacterStatsPanelData` — stats, reputation, panel/header/attributes/skills/inventory text queries, player status, legendary passives
- `LocationTooltipData` — automap panel, window, labels, config, mouse input, tooltip visibility/style/text
- `CompanionRecruitData` — keys, interaction state, NPC query, active companions, map, textures, asset state, combat log
- `DragonBreathData` — keys, time, mount/dragon state, character stats, textures, player/enemy queries, combat events
- `AutomapResizeData` — map, config, panel/container/tile/dot/marker/tooltip queries
- `AutomapUpdateData` — read data, world env, player/text/tile/dot/gas/trap/timed queries
- `LocationMarkerUpdateData` — map, locations, automap, config, player, env, existing markers, container
- `AssetDebugData` — asset source/inventory/catalog, game assets, sound/music assets, archives, sprite packs, debug text
- `EnemyDeathData` — enemy query, character stats, combat events, quest progress, loot generator, rune inventory, faction reps, area
- `SkillMinigameInputData` — minigame state, keys, time, character stats, combat events, skill data
- `PlayerAttackData` — player query, attack flash timer, character stats, combat events, skill cooldowns, status effects, legendary passives
- `DamageProcessData` — damage events, character stats, status effects, legendary passives
- `PuzzleInteractionData` — puzzle state, keys, time, interaction state, character stats, current map, combat events
- `DragonDodgeData` — keys, time, mount state, dragon state, character stats, player/enemy queries, combat events

Type aliases (`PathPreviewQuery`, `ObjectInteractQuery`, `WalkabilityObjectQuery`, `PlayerQueriesSet`, `MusicEntityQuery`) reduce clippy type-complexity warnings. `#[allow(clippy::too_many_arguments)]` added to `CombatSkill::new`, `CombatSkill::new_combo`, and `SpriteAnimation::from_directional_frames`. Clippy warnings drop from 28 to 0.

---

## wow_constructed_languages: Rounds 88–90 — Naigtal/Vanguard, 7-directory sync, shalassian/orcish fixes (110 insertions, 28 files)

### Round 88 — Naigtal, Dimensius, The Vanguard, haranir/nerubian

Updates Naigtal and Dimensius entries in common vocabulary. Adds The Vanguard faction entry. Fixes HTML-MD sync gaps in haranir (grammar, vocabulary) and nerubian (vocabulary).

### Round 89 — 7-directory sync: ethereal, mogu, kalimag, gutterspeak, earthen, qiraji

Fixes ethereal typo/anchors and vocabulary sync. Fixes mogu legend class. Updates kalimag context/links and vocabulary. Fixes gutterspeak warning/nav and vocabulary. Updates earthen CSS. Fixes qiraji description navigation.

### Round 90 — Shalassian nav, orcish IPA, alien-comparative

Fixes shalassian grammar nav links (3 stale `class=new` references). Resolves orcish grammar IPA inconsistency (vowel length marking). Updates alien-comparative link text.

---

## mcp-russia: Migration artifact cleanup, docs rewording, obrashcheniye russification (68 insertions, 11 files)

Removes migration-era language from documentation: `Состояние миграции`→`Текущее состояние`, `Что уже стабильно`→`Что стабильно`, `Архитектурная цель миграции`→`Архитектурная цель`, `При полной миграции`→`Этот сценарий опирается на`, `слой совместимости`→`публичный API`. Renames CI workflow `НИК`→`Непрерывная интеграция`. Updates License copyright from Jonatas Soares to `mcp-russia участники`. Russifies variable `o`→`obrashcheniye` in deloproizvodstvo/tools.py. Adds examples table (10 scenarios) to docs/index.md. Removes stale `Файл использует российские инструменты` footers from example docs.

---

## My-RU-Coverage: Round 89 — ИТ-решения/ИТ-стек calque elimination, ФСФР URL fix (143 insertions, 9 files)

Replaces calques across theme definitions and reports: `ИТ-решения`→`ИТ-продукты`, `ИТ-стек`/`ИТ-стека`/`ИТ-стекам`/`ИТ-стеков`→`ИТ-компоненты`/`ИТ-компонентов`/`ИТ-компонентам`, `решения для предприятий`→`программы для предприятий`, `решения по защите данных`→`системы по защите данных`. Fixes stale ФСФР disclosure URL `fsfm.ru`→`e-disclosure.ru` in BAZIS report. Updates build_themes.py, utils.py aliases, and 3 theme markdown files. Network graph data rebuilt.

---

## ru-skill: Round 108 — CLI/парсинг/legacy revert elimination (33 insertions, 4 files)

Reverts anglicism regressions found in periodic audit: `CLI`→`интерфейс командной строки` in docs/install.md, `парсинг`→`разбор` and 4 instances of `legacy`→`устаревший` in TODO.md. Updates roadmap.md with round 108 status. Adjusts skill-docs.test.js assertions for round/date.

---

## codex-console-english: Rounds 92–93 — scan clean

Round 92 and 93 both scan clean with all 32 tests passing. No translatable non-English content found.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
