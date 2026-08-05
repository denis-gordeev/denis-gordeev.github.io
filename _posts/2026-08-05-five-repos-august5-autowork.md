---
title: "AUTOWORK - Five repos August 5: mcp-russia mypy zero errors, wow_constructed_languages Rounds 100–102, open-divine-divinity helper extraction, otclick v0.47–v0.49, ru-skill round 115"
date: 2026-08-05
layout: post
---

Five monitored repos land new commits since the previous round (August 4). **mcp-russia** eliminates all 127 mypy errors across 18 client modules. **wow_constructed_languages** completes Rounds 100–102 with a repository-wide curly quote normalization, cross-reference and phoneme fixes, and taur-ahe/titan HTML-MD sync. **open-divine-divinity-rust-bevy** extracts helpers from 3 large functions and adds 9 new tests. **otclick** ships three releases (v0.47–v0.49) with security fixes, rate-limit enforcement, Docker improvements, and Python 3.12 upgrade. **ru-skill** round 115 removes residual API calques in JSDoc and SSR pages.

## mcp-russia: Zero mypy errors in 18 client modules

Resolves all 127 mypy errors across 18 client modules in a single pass. Key patterns: HTTP wrappers returned as Any with isinstance narrowing (РосАПИ, ЦБ РФ); str() casts for object values (Росгидромет, Росводресурсы); isinstance guards for dict/list parameters (Закупки, КАД Арбитр); unique parameter names (Росприроднадзор, Совет Федерации, Казначейство); explicit dict[str, str] types (Росреестр, ФНС). Result: 0 mypy errors in 216 files, 691 tests pass. 20 files changed, 280 insertions, 194 deletions.

---

## wow_constructed_languages: Rounds 100–102

### Round 100: Repository-wide curly quote normalization and CSS completion

Audits nature/ and normalizes all curly quotes to straight quotes across all 30 language directories. Adds missing CSS rules (h4, .warning, .shared, a:hover) and normalizes h4 color styling. Completes the HTML-MD sync initiative started in Round 99. 84 files changed, 1655 insertions, 1410 deletions.

### Round 101: Factual phoneme fix, heading hierarchy, cross-references

Fixes a factual phoneme error in common/vocabulary.md, corrects heading hierarchy and CSS classes in drust/sethrak/shath-yar/vulpera HTML files, adds cross-references and IPA wrappers. 13 files changed, 49 insertions, 34 deletions.

### Round 102: taur-ahe and titan HTML-MD sync

Fixes factual errors, IPA wrappers, section reorder, CSS, and anchors in taur-ahe (description, grammar, vocabulary) and titan (description, grammar, vocabulary). 10 files changed, 153 insertions, 132 deletions.

---

## open-divine-divinity-rust-bevy: Helper extraction from 3 large functions

Extracts helper functions from three of the largest functions in game.rs:

- **spawn_trap_elements_in_area** (435→~100 lines + 4 helpers): spawn_gas_valve_and_zone, spawn_collapsing_floor_set, spawn_speed_shrine_and_escape, register_trap_progress
- **handle_dialog_response_keys** (377→~100 lines + 2 helpers + static): dialog_reward_item, apply_dialog_reward, DIALOG_QUEST_TRIGGERS
- **update_enemy_ai** (425→~183 lines + 5 helpers): effective_aggression_range, effective_attack_cooldown, boss_preferred_skill_index, update_boss_phase_and_enrage, try_boss_special_attacks

Adds 9 new tests. Test count: 1190→1199. 2 files changed, 979 insertions, 946 deletions.

---

## otclick: v0.47.0, v0.48.0, v0.49.0

### v0.47.0: UX maxlength, revokeObjectURL fix, type annotations, dedup

Adds maxlength=500 to search inputs, fixes URL.revokeObjectURL timing in exportCsv(), adds 7 missing type annotations across es.py/db.py/db_pool.py/assets.py, deduplicates _serialize_value by reusing _json_safe from parsing.py. 11 files changed.

### v0.48.0: Security fixes, rate limit enforcement, robustness

P0 fixes: rate limiting was a no-op (_late_limit decorator never enforced), timing attack on API key comparison (now uses hmac.compare_digest), incorrect search route return type. P1: diagnose_migrations crash fix, redundant IS NULL simplification, rollback on DB error in upsert_reviews. P2: YAML anchors for Docker Compose DRY, Dockerfile chown for non-root user, ES ping cache (5s TTL), root logger config, shared _env_flag extraction. P3: remove public ports for redis/postgres, fix mixed EN/RU labels, fix exportCsv DOM cleanup. 447 tests pass, 100% measured coverage. 20 files changed, 252 insertions, 73 deletions.

### v0.49.0: Remove api.py re-exports, split Docker deps, Python 3.12

Removes 48 lines of backward-compat re-exports from api.py (19 noqa: F401 imports); tests now import directly from source modules. Adds healthchecks to Docker Compose for postgres and elasticsearch. Creates requirements-api.txt without dagster dependencies for the API image. Upgrades base image from python:3.11-slim to python:3.12-slim. 9 files changed, 125 insertions, 126 deletions.

---

## ru-skill: Round 115 — Residual API calques in JSDoc and SSR pages

Eliminates remaining "API" calques in yandex-rasp JSDoc and "SSR-страницы" in zoon-nearby package.json. Updates roadmap and regression tests. 5 files changed, 33 insertions, 10 deletions.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
