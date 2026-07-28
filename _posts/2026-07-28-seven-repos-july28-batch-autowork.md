---
title: "AUTOWORK - Seven repos July 28: wow round 95 anchor normalization, divine-divinity 104 new tests and combat/skills extraction, otclick Alembic migrations and API v0.42.0, ru-coverage rounds 90–91, ru-skill rounds 110–111 jargon audit, mcp-russia URI fixes, codex-console round 95 phrasing fix"
date: 2026-07-28
layout: post
---

Seven monitored repos land new commits since the previous round. **wow_constructed_languages** round 95 fixes HTML-MD sync for shath-yar, darnassian, and zandali. **open-divine-divinity-rust-bevy** adds 104 new unit tests (1013→1117) with major helper extraction in combat, skills, quests, and crafting modules. **otclick** introduces Alembic migration support, advisory lock, diagnostics CLI, and bumps API to v0.42.0. **My-RU-Coverage** completes russification rounds 90–91. **ru-skill** audits jargon in rounds 110–111. **mcp-russia** fixes URI resources and typo corrections. **codex-console-english** round 95 fixes awkward phrasing in utils.py.

## wow_constructed_languages: Round 95 — HTML-MD sync fixes (shath-yar, darnassian, zandali)

Normalizes investigation anchors, corrects factual errors and heading hierarchy in darnassian grammar/vocabulary, fixes cross-references in shath-yar vocabulary, and resolves annotation mismatches in zandali grammar and vocabulary. 11 files changed across three language directories.

---

## open-divine-divinity-rust-bevy: 104 new tests, helper extraction, zero clippy warnings

### 54 new tests (1013→1067): extract process_damage_events, handle_skill_minigame_input

Extracts `process_damage_events` and `handle_skill_minigame_input` as standalone helpers from the monolithic game.rs. Eliminates redundant closures and `assigning_clones` lint across assets, audio, cmp_archive, cpacked_index, layout, save_load, skills, sprite_animation, status_effects, text_assets, textures, and world_data modules. 18 files touched with 1445 insertions and 999 deletions.

### 50 new tests (1067→1117): extract build_dialog_tree_from_text, create_initial_quests, crafting_recipes helpers

Further extraction of `build_dialog_tree_from_text`, `create_initial_quests`, and `crafting_recipes` helpers. New `Quest` and `CraftingRecipe` constructors. Combat module grows to 2125 lines, player_stats to 2450, quests to 723, crafting to 878. Zero clippy warnings remain.

---

## otclick: Alembic migrations, advisory lock, diagnostics CLI — API v0.40.0→v0.42.0

### Alembic migration support (v0.40.0)

Adds `dwh/alembic/` directory with env.py, script.py.mako, and initial migration 001_initial_schema (table + 7 indexes). Introduces `SCHEMA_MIGRATION_MODE` env var (legacy|alembic, default: legacy) in db.py with `_init_schema_config()`, `run_alembic_migration()`, and `ensure_schema()` delegation. 8 new tests.

### Hardened Alembic runtime, legacy schema bootstrap (v0.40.0)

Fixes Alembic migration runtime edge cases and adds safe legacy schema bootstrapping via `safely bootstrap legacy schema for Alembic`.

### Migration one-shot service, advisory lock, diagnostics CLI (v0.41.0)

Adds a one-shot migration service with advisory lock to prevent concurrent migrations. Introduces a diagnostics CLI for migration state inspection. Integration tests added.

### Config consistency, coverage omit fix, db.py bootstrap tests (v0.42.0)

Fixes config consistency issues, corrects coverage omit patterns, and adds db.py bootstrap tests. 18 files changed with 977 insertions across the migration stack.

---

## My-RU-Coverage: Русификация rounds 90–91

### Round 90 — CSPC→ЦСПЦ, SCM→СКМ, АВС→Амазон Веб Сервисы

Replaces anglicized abbreviations with Russian equivalents. Fixes SLA terminology inconsistencies across the knowledge base.

### Round 91 — Байкал Электроник→Электроникс, ТЕМЫ_RU→ТЕМЫ_РФ, markdown→мд

Continues russification: fixes brand name (Электроник→Электроникс), replaces RU with РФ in section headers, translates technical terms (markdown→мд, ISS→ИСС), replaces `lambda x` with пара/эл, and russifies English variable names. 16 files changed including scripts, graph data, and wikilinks.

---

## ru-skill: Rounds 110–111 — jargon audit and legacy revert elimination

### Round 110 — audit jargon: train-search, npm-скриптов, CLI in product names

Audits remaining jargon across skill definitions and documentation, identifying anglicisms in train-search references, npm script naming, and CLI usage in product name contexts.

### Round 111 — eliminate CLI and cookie reverts in delivery-tracking

Removes residual CLI and cookie terminology reverts from delivery-tracking module. Updates regression tests to match. 13 files changed with roadmap additions and skill documentation updates.

---

## mcp-russia: URI fixes, typo corrections, README cleanup

Fixes URI resources for deloproizvodstvo, corrects typo konsulitirovat→konsultirovat, cleans up README, fixes example parameters, and renames _e2e→_skvozn (end-to-end→сквозной) in test naming.

---

## codex-console-english: Round 95 — fix awkward phrasing in utils.py docstring

Fixes awkward English phrasing in utils.py docstring. All tests continue to pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
