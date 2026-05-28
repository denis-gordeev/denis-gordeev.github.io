---
title: "AUTOWORK - autowork gains self-healing doctor and sync history, mcp-russia reaches 16 modules"
date: 2026-05-28
layout: post
---

Two commits on May 27 brought **autowork** from observable to self-repairing: a `doctor --self-heal` command that regenerates drifted wrappers, a sync history ring buffer, and collision-aware cron scheduling. Meanwhile, **mcp-russia** added three more Russian data modules — FNS, Rosreestr, and FSSP — bringing the total to 16, and migrated Portuguese function names to Russian across seven existing modules.

## autowork: self-healing and operational memory

### `doctor --self-heal`

The `doctor` command now accepts a `--self-heal` flag. When drift is detected in controller or managed wrappers, instead of merely reporting the problem, `--self-heal` regenerates the drifted files in-place. This eliminates the most common manual remediation step in daily operations: finding the exact `autowork wrap` invocation to fix a single drifted file.

### Sync history ring buffer

`State.telegram_sync_history` now stores the last 10 Telegram sync round summaries (replacing the single `last_telegram_sync` field). Both `review` and `review --json` expose this history with aggregate statistics — handled total, ignored breakdown by reason, and timestamp — so operators can spot trends like increasing ignore counts or dispatch failures over time without digging through logs.

### Per-project dispatch outcomes

The `review` output now includes per-project dispatch outcomes, showing whether each project's last cron run succeeded, failed, or was skipped. Combined with sync history, this gives a complete picture of portfolio health from a single command.

### Collision-aware cron scheduling

The cron minute assignment logic was updated to be collision-aware: when scheduling daily runs for multiple projects, the system now prefers the nearest free minute slot rather than silently assigning overlapping schedules. This prevents two projects from competing for the same minute on a shared host.

### Root wrapper drift fix

A regression where the controller-root `autowork.sh` had drifted from the portfolio-wide flow was fixed by restoring the correct template.

### Regression tests

Five new tests cover:

- `doctor --self-heal` regenerates drifted wrappers
- Sync history is persisted and limited to 10 entries
- `review --json` includes sync history with aggregate stats
- Collision-aware cron prefers nearest free slot
- Per-project dispatch outcomes appear in review output

## mcp-russia: 16 modules, Portuguese-to-Russian migration

A single large commit (61 files changed, +2,300 lines) added three new Russian government data modules and completed the Portuguese-to-Russian naming migration.

### FNS — Federal Tax Service

The new **fns** module provides stubs for Russia's Federal Tax Service (ФНС):

- 9 tools covering INN lookups, tax debt queries, EGRUL/EGRIP extracts, and VAT rate references
- 3 resources for reference data (tax types, OKVED sections, inspection codes)
- 2 prompts (tax compliance analysis, EGRUL overview)
- Full constants for tax types, inspection codes, and OKVED mappings

### Rosreestr — Federal Registry Service

The **rosreestr** module covers Russia's Federal Service for State Registration, Cadastre and Cartography:

- 8 tools for cadastral object lookups, property rights searches, and land category queries
- 3 resources (cadastral zones, land categories, property types)
- 2 prompts (property analysis, cadastral overview)
- Constants for cadastral status codes, land categories, and property type classifications

### FSSP — Federal Bailiff Service

The **fssp** module provides data stubs for Russia's Federal Bailiff Service:

- 8 tools for enforcement proceeding lookups, debtor searches, and fine tracking
- 3 resources (proceeding categories, enforcement types, debt statuses)
- 2 prompts (debt analysis, enforcement overview)
- Constants for proceeding categories, enforcement types, and status codes

### Portuguese-to-Russian name migration

Seven existing modules had their internal function names, docstrings, and variable names migrated from Portuguese to Russian:

- **cbrf** — `comparar_moedas` → `сравнить_валюты`, `obter_cotacao` → `получить_котировку`, etc.
- **gosduma**, **publikatsii**, **rosaudit**, **rosgidromet**, **rosstat**, **rosvodresursy** — client function names and docstrings updated

This migration makes the codebase internally consistent: all 16 modules now use Russian-language identifiers throughout, matching the Russian-language tool descriptions exposed to LLM clients.

## All 16 modules

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

## The self-sustaining loop

These updates close an important loop in Denis's infrastructure. The autowork orchestrator can now detect its own drift and repair it (`--self-heal`), remember its own operational history (sync ring buffer), and schedule itself without collisions. Meanwhile, mcp-russia continues to expand the Russian-language data surface available to AI tools, now covering 16 federal agencies with internally consistent Russian-language code. The next milestone for mcp-russia will be replacing stubs with real API integrations; the next milestone for autowork will be using its own sync history to drive automated anomaly detection.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
