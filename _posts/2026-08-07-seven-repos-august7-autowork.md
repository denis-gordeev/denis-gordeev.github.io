---
title: "AUTOWORK - Seven repos update: wow Rounds 107–108, mcp-russia МВД + Ростехнадзор, divine-divinity helper extraction, otclick v0.52–v0.53, ru-skill Round 119, ru-coverage Round 98, codex-console Round 103"
date: 2026-08-07
layout: post
---

Seven monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## wow_constructed_languages: Rounds 107–108 — CSS normalization, HTML-MD sync

**Round 107** performs repository-wide CSS normalization phase 2, IPA fixes, and comparative HTML consistency across 90 files. Standardized CSS classes and IPA markup across all language directories (alien, darnassian, drust, dwarven, earthen, elven, eredun, ethereal, gnomish, gutterspeak, haranir, kalimag, mogu, nature, nazja, nerglish, nerubian, orcish, pandaren, qiraji, sethrak, shath-yar, taur-ahe, thalassian, titan, tolvir, vrykul, vulpera, zandali) plus comparative pages and example sentences. 91 files changed, 459 insertions, 405 deletions.

**Round 108** applies HTML-MD sync fixes to ethereal, shath-yar, and zandali: corrected a factual error, fixed nav order, replaced bare `—` delimiters, removed markdown artifacts, added h5 CSS, and repaired a broken link. 12 files changed, 215 insertions, 192 deletions.

---

## mcp-russia: МВД and Ростехнадзор modules, network contract tests

Major module expansion:

- **МВД России (mvd)**: 8 new tools — crime statistics, traffic accidents, wanted persons, drug crimes, reference data; CSV parsing of open data.gov.ru datasets; fallback data for 2024; 3 resources, 2 prompts.
- **Ростехнадзор**: 7 new tools — OPO incidents, licenses, OPO registry, reference data; CSV parsing; fallback data for 2024; 3 resources, 2 prompts.
- **Рособрнадзор**: 4 new tools — universities with admission bans, control statistics, inspection results, expert registry.
- **Госдума**: Added `avtor` and `sootvetstvie` parameters to zakonoproekty.
- **Совет Федерации**: New tool `poimennoe_golosovanie` (roll-call voting).
- **Росприроднадзор**: New tool `poisk_lesnogo_nadzora` (forestry supervision search).
- **Закупки**: New tool `poisk_rnp` (registry of unreliable suppliers).
- **Казначейство**: 3 new tools — budget sections, subsections, budget estimates; `razdel`/`podrazdel` parameters in budget execution.

Added optional network contract tests (`MCP_RUSSIA_NETWORK_TESTS=1`). features.md now lists 26 modules, 244 tools. 823 tests pass, mypy strict, lint, format all clean. 50 files changed.

---

## open-divine-divinity-rust-bevy: Extract 7 functions into 28 helpers

Continued the refactoring streak — extracted 7 large functions into 28 helper functions:

- `handle_skill_hotkeys` (216→200): extracted `apply_mana_cost_with_legendary`, `compute_skill_total_damage`, `apply_life_drain_heal`
- `handle_rune_combo_input` (209→65): extracted `rune_digit_index`, `select_rune_slot`, `apply_fusion_stat_bonuses`, `perform_rune_fusion`, `perform_legendary_fusion`
- `handle_inventory_sort_filter` (185→55): extracted `cycle_sort_mode`, `cycle_filter_mode`, `filtered_inventory_count`, `filtered_inventory_indices`, `perform_inventory_swap`
- `update_enemy_ai` (183→157): extracted `compute_aggression_multiplier`, `move_enemy_towards`, `move_enemy_away`, `send_enemy_attack`, `detect_player_stealth`
- `handle_dialog_interaction` (151→70): extracted `companion_dialog_tree_for_npc`, `reputation_based_start_node`, `trigger_npc_quest_progress`
- `handle_merchant_input` (150→60): extracted `merchant_digit_key_index`, `execute_merchant_buy`, `execute_merchant_sell`, `execute_merchant_haggle`
- `handle_crafting_input` (149→70): extracted `crafting_digit_index`, `compute_crafting_gold_cost`, `compute_crafting_success_chance`, `crafting_failure_reason`

Fixed 9 `too_many_arguments` + 1 `&mut Vec` clippy warnings → 0 warnings. 16 new unit tests (1262→1278). 2 files changed, 2329 insertions, 1598 deletions.

---

## otclick: v0.52.0 and v0.53.0

**v0.52.0**: Fixed Docker healthcheck, added API_BASE environment variable fallback, normalized rate_limit naming across codebase and tests, deduplicated model definitions in reviews DWH, added CI rules in .gitlab-ci.yml, updated .gitignore. 12 files changed.

**v0.53.0**: Added `TRUSTED_PROXIES` configuration for rate limiting behind reverse proxies, added restart policies (`unless-stopped`) in docker-compose, added 64 new rate limit tests for proxy handling. 6 files changed, 101 insertions, 9 deletions.

---

## ru-skill: Round 119 — SSR format consistency

Round 119 eliminates SSR format inconsistency in `yandex-market-search` documentation. Updated roadmap. 3 files changed.

---

## My-RU-Coverage: Round 98 — russification

Replaced «логистические» with «транспортно-складские» (TATN sector), replaced «Windows» with «Виндовс» in 2 scripts, updated graph data. 6 files changed, 129 insertions, 118 deletions.

---

## codex-console-english: Round 103 — Chinese-English calque fixes

Fixed ~42 Chinese-English calques across 20 files: *returns None when timeout* → *or None on timeout*, *Total time spent* → *elapsed*, *polling N times* → *after N polls*, *batch operation* → *batch actions*, *tool library* → *utility library*, and many more. All 32 tests pass. 20 files changed, 99 insertions, 50 deletions.
