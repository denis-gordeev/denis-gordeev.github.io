---
title: "AUTOWORK - autowork gains per-project healing, mcp-russia reaches 18 modules, My-RU-Coverage completes Russian-only pipeline"
date: 2026-05-29
layout: post
---

Since yesterday's post, Denis Gordeev's **autowork** orchestrator has deepened its self-healing capabilities with per-project granular drift reporting across all JSON surfaces, **mcp-russia** has completed a second wave of Portuguese-to-Russian migration bringing the total to 18 modules and 1,896 tests, and **My-RU-Coverage** has eliminated all legacy Taiwan/Chinese scripts to become a fully Russian-only coverage pipeline.

## autowork: per-project healing visibility

Three commits on May 28 extended the self-healing infrastructure introduced earlier this week from project-agnostic to per-project granular.

### `run --self-heal`

The `run` command now accepts `--self-heal`, regenerating drifted controller and managed wrappers before syncing projects. This extends the healing surface from `doctor --self-heal` and `review --self-heal` to the primary execution path — so an unattended cron run can now detect and repair drift automatically before dispatching.

### `telegram-sync --json --self-heal`

The `telegram-sync` command combines both JSON output and self-healing: when drift is detected during a sync, wrappers are regenerated, and the JSON payload reports which project-specific wrappers were healed. The `--self-heal` flag now works across `doctor`, `review`, `run`, and `telegram-sync`.

### `history --until`

The `history` subcommand now accepts `--until` for upper-bound timestamp filtering, complementing `--since` for range queries. Combined with `--limit`, operators can precisely window their operational history.

### Per-project granular drift mappings

`wrapper_contract_status` now accepts an optional state parameter and returns `per_project_healed` and `per_project_drifted` dicts mapping project slugs to their healed or drifted wrapper paths. All JSON output surfaces — `telegram-sync --self-heal --json`, `review --json`, `doctor --format json --self-heal`, and `run --format json --self-heal` — include these per-project mappings. This means that instead of knowing "3 wrappers drifted," operators now know exactly which project's wrappers drifted and which were healed.

## mcp-russia: second migration wave, 18 modules

A single commit (3,571 additions, 643 deletions) completed the second wave of Portuguese-to-Russian migration across the entire mcp-russia codebase.

### `format_brl` → `format_rub`, `parse_brl_number` → `parse_rub_number`

The Brazilian real formatting functions have been replaced with Russian ruble equivalents:

- `format_rub` outputs `1 234,56 ₽` instead of `R$ 1 234,56`
- `parse_rub_number` handles both comma and period as decimal separators for backward compatibility
- `format_brl` and `parse_brl_number` are preserved as deprecated aliases
- 90+ call sites updated across the entire project

### Infrastructure names → Russian

Portuguese class and function names in the infrastructure layer have been migrated:

- `EtapaPlano` → `EtapPlana`, `PlanoConsulta` → `PlanZaprosa`
- `planejar_consulta_impl` → `splanirovat_zapros_impl`
- `recomendar_tools_impl` → `rekomendovat_instrumenty_impl`
- Portuguese strings → Russian throughout

### Server MCP tools renamed

The four root-level meta-tools, partially translated in the previous commit, now have fully Russian identifiers:

| Old name | New name |
|----------|----------|
| `listar_features` | `spisok_funktsiy` |
| `recomendar_tools` | `rekomendovat_instrumenty` |
| `planejar_consulta` | `splanirovat_zapros` |
| `executar_lote` | `vypolnit_paket` |

### `McpBrasilError` → `McpRussiaError`

The root exception class has been renamed from `McpBrasilError` to `McpRussiaError`, with `McpBrasilError` preserved as an alias for backward compatibility.

### 18 modules, 1,896 tests

All 1,896 tests pass, and `ruff check` reports no violations. The two new modules added in the previous commit (GIBDD and Minobrnauki) bring the total to 18:

| Module | Agency | Tools | Resources | Prompts |
|--------|--------|-------|-----------|---------|
| cbrf | Central Bank | 9 | 3 | 2 |
| rosstat | Rosstat | 8 | 3 | 2 |
| gosduma | State Duma | 6 | 2 | 2 |
| rosapi | ROSAPI | 8 | 2 | 2 |
| zakupki | Procurement | 7 | 2 | 2 |
| minzdrav | Minzdrav | 8 | 3 | 2 |
| kad_arbitrazh | Arbitration Court | 7 | 2 | 2 |
| rosaudit | Audit Chamber | 5 | 2 | 2 |
| rosgidromet | Meteorology | 5 | 2 | 2 |
| rosvodresursy | Water Resources | 5 | 2 | 2 |
| publikatsii | Publications | 7 | 2 | 2 |
| rospotrebnadzor | Consumer Rights | 7 | 3 | 2 |
| roskomnadzor | Communications | 11 | 3 | 2 |
| fns | Tax Service | 9 | 3 | 2 |
| rosreestr | Registry/Cadastre | 8 | 3 | 2 |
| fssp | Bailiff Service | 8 | 3 | 2 |
| gibdd | Traffic Police (MVD) | 12 | 3 | 2 |
| minobrnauki | Education & Science | 12 | 3 | 2 |

## My-RU-Coverage: full Russian-only pipeline

The **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** repository, which tracks MOEX (Moscow Exchange) stock coverage and enrichment data, completed its localization with two commits on May 28.

### Removal of legacy Taiwan scripts and batch workflow

The largest commit removed 1,309 lines of legacy Taiwan-oriented scripts and batch workflow code (replaced by 80 lines of Russian-only equivalents). This eliminates the last non-Russian data pipeline in the repository.

### Purge of Chinese regex and English remnants

A follow-up commit removed Chinese regex patterns from `update_enrichment` and translated remaining English strings in script docstrings. Legacy generators were deprecated with clear migration paths.

The repository now operates as a fully Russian-language pipeline: all scripts, patterns, and data flows target MOEX and Russian market data exclusively.

## codex-console-english: translation verification continues

Rounds 16 and 17 of English translation verification on May 28 confirmed no non-English text remains. All 29 tests continue to pass.

## The localization pattern

This round illustrates a consistent pattern across Denis's repositories: systematic replacement of legacy Portuguese/Brazilian identifiers (from the mcp-brasil origins) and Chinese/Taiwanese artifacts (from the taiwan-md/My-RU-Coverage origins) with Russian-language equivalents. The autowork orchestrator's per-project healing ensures that this kind of large-scale refactoring across managed repositories can be detected and repaired automatically — a self-sustaining infrastructure that can maintain its own consistency.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
