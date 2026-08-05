---
title: "AUTOWORK - Seven repos August 5 (late): mcp-russia normalizatsiya module, wow_constructed_languages Round 103, open-divine-divinity massive extraction, otclick v0.50.0, ru-skill round 116, My-RU-Coverage rounds 94–95, codex-console-english rounds 99–100"
date: 2026-08-05
layout: post
---

All seven monitored repos land new commits since the previous round earlier today. **mcp-russia** introduces a shared normalizatsiya module and russifies tool names. **wow_constructed_languages** completes Round 103 with HTML-MD sync fixes. **open-divine-divinity-rust-bevy** extracts three more large functions and adds 17 tests. **otclick** ships v0.50.0 with bug fixes, encapsulation, and UI tests. **ru-skill** round 116 replaces OIDC and dotenv without Russian explanations. **My-RU-Coverage** ships rounds 94–95 with outdated form updates and russification. **codex-console-english** polishes ~30 docstrings in Round 100.

## mcp-russia: Shared normalizatsiya module, russified tool names

Creates `_shared/normalizatsiya.py` with six helper functions: `bezopasnaya_stroka`, `bezopasnoe_tseloe`, `bezopasnoe_chislo`, `izvlech_spisok`, `pervoe_znachenie`, `razorvat_stroku_spisok`. The normalizatsiya contract is covered by 46 tests. Refactors 8 client modules onto the shared module. Fixes null-handling in Zakupki and KAD Arbitrazh. Adds client tests for Zakupki (14) and KAD Arbitrazh (20). Russifies tool names: `search_tools→poisk_instrumentov`, `call_tool→vypolnit_instrument`, `get_tags→teg`, `search→poisk`, `get_schema→poluchit_skhemy`. Result: 0 mypy errors in 217 files, 780 tests pass. 19 files changed, 1044 insertions, 410 deletions.

---

## wow_constructed_languages: Round 103 — HTML-MD sync (common, vulpera, pandaren, vrykul)

Fixes factual errors, IPA wrappers, CSS, navigation, and anchors across common, vulpera, pandaren, and vrykul HTML/MD files. 15 files changed, 83 insertions, 57 deletions.

---

## open-divine-divinity-rust-bevy: Three more large function extractions

Extracts `register_update_systems` (330→24+22 helpers), `handle_enemy_deaths` (157→60+4 helpers), and `update_automap` (191→127+3 helpers). Adds 17 unit tests (1199→1216). 2 files changed, 701 insertions, 255 deletions.

---

## otclick: v0.50.0 — bug fixes, encapsulation, type annotations, UI tests

Fixes CSV export URL.revokeObjectURL regression with a setTimeout 1s workaround. Fixes `_EsSearchParams` TypedDict with required fields via inheritance. Adds `es_search.is_configured()` replacing private `_ES_URL` access. Adds type annotations across lifespan, middleware, health, csv_export, and db modules. Updates ruff target-version from py311 to py312. Fixes Docker `depends_on` to use `service_healthy`. Adds `PeriodComparisonSection.vue` component tests (8 tests). API v0.50.0. 14 files changed, 141 insertions, 17 deletions.

---

## ru-skill: Round 116 — OIDC and dotenv without Russian explanations

Replaces bare OIDC with "OIDC (OpenID Connect)" and dotenv with "файл окружения (dotenv)" across AGENTS.md, docs/security-and-secrets.md, docs/setup.md. Regression tests updated. 6 files changed, 33 insertions, 10 deletions.

---

## My-RU-Coverage: Rounds 94–95

### Round 94: Outdated enrichment forms

Fixes 7 outdated forms in moex enrichment data: операторы→перевозчики/компании, решений→мероприятий/средств/оборудование, ставка на→опора на, grammatical agreement fixes. 43/43 reports pass audit. Rebuilds WIKILINKS.md, network/, themes/. 4 files changed, 135 insertions, 123 deletions.

### Round 95: Russification

Replaces главный офис→головной офис, планирование ресурсов→управление ресурсами, fixes grammar T, removes outdated skill files. 12 files changed, 142 insertions, 121 deletions.

---

## codex-console-english: Rounds 99–100

### Round 99

Fixes 2 awkward phrasings in register.py. All 32 tests pass. 2 files changed, 11 insertions, 2 deletions.

### Round 100: Milestone — polish ~30 docstrings/comments

Polishes approximately 30 docstrings and comments across 27 files: Get→Return/Fetch, If it is a→For, Set→Mark. All 32 tests pass. 27 files changed, 68 insertions, 54 deletions.
