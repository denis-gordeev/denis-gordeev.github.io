---
title: "AUTOWORK - autowork gains observability, mcp-russia reaches 13 modules with full test coverage"
date: 2026-05-27
layout: post
---

Since yesterday's update, Denis Gordeev's **autowork** orchestrator has received significant observability improvements — persisted Telegram sync summaries, machine-readable review output, and failure-path regression tests — while **mcp-russia** has completed its Roskomnadzor and Rospotrebnadzor modules, bringing the total to 13 Russian data modules with comprehensive test coverage.

## autowork: from fire-and-forget to observable

Two commits on May 26 brought the autowork controller from a system that only printed status to stdout toward one that persists operational health and exposes it to downstream tooling.

### Persisted Telegram sync summary

Previously, the `telegram-sync` command reported handled and ignored counts to stdout but forgot them after each run. Now the summary is persisted in `State.last_telegram_sync` as a `TelegramSyncSummary` dataclass containing:

- **handled**: count of dispatched Telegram updates
- **ignored**: breakdown by reason (e.g. `non_message`, `no_topic_match`)
- **timestamp**: ISO timestamp of the sync

The `review` command now surfaces this summary in both its text output and the new JSON payload, so unattended cron runs expose bot health without needing raw stdout logs.

### `review --json`: machine-readable portfolio state

A new `--json` flag on the `review` command outputs structured JSON with:

- Wrapper contract status (controller + managed, with drifted paths)
- Full project list with slugs, branches, daily run targets, fork status, and Telegram topic IDs
- Last Telegram sync summary (or `null` if never synced)

This enables cron dashboards and monitoring systems to consume portfolio health without parsing plain text.

### `doctor` surfaces guaranteed env keys

The `doctor` command now lists the guaranteed project-runtime env keys (`AUTOWORK_CONTROLLER_ROOT`, `AUTOWORK_PROJECT_SLUG`, `TG_TOPIC_ID`, `AUTOWORK_TG_DIR`), so downstream tools can see exactly which metadata keys are available at dispatch time.

### Shell template base commands

When `AUTOWORK_BASE_COMMAND` contains `$PROMPT`, the controller now runs it as a shell template via `/bin/zsh`, injecting the prompt as the `PROMPT` environment variable. This supports base commands like `opencode run -m "$MODEL" --dangerously-skip-permissions -- "$PROMPT"`, enabling more flexible integration with different LLM frontends.

### Drift remediation hints

Both `review` and `doctor` now emit remediation hints when wrapper drift is detected — telling operators the exact command to regenerate drifted wrappers instead of only showing the failing file path.

### Failure-path regression tests

New test coverage ensures that:

- `telegram-sync` returns exit code 1 when `get_updates` raises `TelegramError`
- The Telegram sync summary is correctly persisted after successful syncs
- `review --json` outputs valid structured JSON with the expected schema
- `doctor` includes the guaranteed runtime env keys in its output

## mcp-russia: 13 Russian modules, full test coverage

The **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** repository completed two major modules and added tests for all 13 Russian data modules in a single commit (61 files, +3,314 lines).

### Roskomnadzor module

The new **roskomnadzor** module provides data stubs for Russia's Federal Service for Supervision of Communications, Information Technology, and Mass Media:

- 11 tools covering license lookups, media registry searches, personal data operator queries, and violation tracking
- 3 resources for reference data (activity directions, license types, violation categories)
- 2 prompts (violation analysis, registry overview)
- Full constants covering registry types, media categories, personal data operator categories, and violation classifications
- All API functions are stubs pending real integration with rkn.gov.ru

### Rospotrebnadzor module

The **rospotrebnadzor** module was updated from a placeholder to a complete module for Russia's Federal Service for Surveillance on Consumer Rights Protection and Human Wellbeing:

- `__init__.py` now uses proper `FeatureMeta` with Russian-language tags
- Prompt imports fixed from the nonexistent `fastmcp.prompts.base` to the working FastMCP 3.x API (`PromptResult`, `Message`, `PromptMessage`)

### Server meta-tools translated to Russian

The four root-level meta-tools — `listar_features`, `recomendar_tools`, `planejar_consulta`, `executar_lote` — had their docstrings and examples translated from Portuguese to Russian. The `executar_lote` examples now reference Russian tools (gosduma, cbrf) instead of Brazilian ones.

### Full test suite: 1,815 tests passing

Tests were added for all 13 Russian modules (unit + integration for each):

| Module | Unit tests | Integration tests |
|--------|-----------|-------------------|
| cbrf | 11 | 6 |
| rosstat | 10 | 6 |
| gosduma | 8 | 6 |
| rosapi | 10 | 6 |
| zakupki | 9 | 6 |
| minzdrav | 10 | 6 |
| kad_arbitrazh | 9 | 6 |
| rosaudit | 7 | 6 |
| rosgidromet | 7 | 6 |
| rosvodresursy | 7 | 6 |
| publikatsii | 9 | 6 |
| rospotrebnadzor | 9 | 5 |
| roskomnadzor | 11 | 5 |

All 1,815 tests pass, and `ruff check` reports no violations.

### Bug fixes

- **cbrf/tools.py**: `comparar_moedas` used `*codigos: str` which FastMCP does not support — replaced with `codigos: list[str] | None = None`
- **rosapi/prompts.py**: imported `UserMessage` from `fastmcp` (nonexistent) — replaced with FastMCP 3.x API

## codex-console-english: ASCII cleanup

The **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** repository received a minor cleanup commit on May 27: invisible zero-width space characters (U+200B) in `src/config/constants.py` and a Unicode arrow (`→`) in `src/services/moe_mail.py` were replaced with ASCII equivalents. All 29 tests continue to pass.

## The evolving toolchain

The autowork observability improvements and mcp-russia module completions illustrate a pattern in Denis's recent work: building infrastructure that can monitor itself. The autowork orchestrator now persists its own health data, exposes it in machine-readable form, and tests its own failure modes — while mcp-russia provides the data layer that Russian-language AI tools need to operate, with full test coverage ensuring reliability as real API integrations replace stubs.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
