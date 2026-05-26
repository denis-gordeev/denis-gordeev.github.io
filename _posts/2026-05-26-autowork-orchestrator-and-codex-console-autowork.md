---
title: "AUTOWORK - Denis Gordeev builds a local-first repo orchestrator and English-language Codex console fork"
date: 2026-05-26
layout: post
---

Since the last update in April, Denis Gordeev has launched two notable new repositories: **autowork**, a local-first automation orchestrator for managing portfolios of git repositories, and **codex-console-english**, an English-language fork of a Chinese OpenAI Codex registration console with compatibility fixes and translation work.

## autowork: a local-first repo orchestrator

The **[autowork](https://github.com/denis-gordeev/autowork)** repository is a Python-based controller that automates work across a folder of git repositories. Each repository gets its own `autowork.sh` wrapper, cron schedule, Telegram topic, and local mirror folder. The controller then dispatches tasks to an LLM-powered base command on a configurable schedule.

This is the tool that powers the AUTOWORK-tagged posts on this very site — the orchestrator scans repositories, reads their `AUTOWORK_INSTRUCTIONS.md`, inspects open issues and PRs, and builds a prompt that tells the agent what to work on next.

### How each round works

For every managed repository, the controller:

1. Discovers the repo and stores it in `data/state.json`
2. Creates or refreshes the per-repo `autowork.sh` wrapper
3. Hydrates `.autowork/project.env` with project metadata
4. Creates a Telegram topic (when configured) and local mirror folders
5. Refreshes the managed cron block

A single project run builds a prompt from:

1. `AUTOWORK_INSTRUCTIONS.md` — project-specific policy
2. Open issues and PRs/MRs
3. TODO items from `README.md` and `TODO.md`

If the repository is a fork, the controller also attempts to merge upstream changes before dispatching work.

### Telegram integration

The orchestrator integrates with a Telegram bot to create one forum topic per repository. Inbound messages are matched by `message_thread_id`, mirrored to both a local inbox and the Telegram mirror root, and then forwarded to the base command in that repository. This enables ad-hoc task dispatch via Telegram alongside the scheduled cron runs.

### Cron scheduling

The controller manages its own crontab block, staggering managed project runs across different minutes within the hour. Each project gets a configurable number of daily runs (default: 2), and the controller persists a per-project `cron_minute` so existing repositories keep their assigned slot even when the portfolio changes.

### Living task lists

Each managed repository is expected to maintain a living task list in `TODO.md` (or a TODO section in `README.md`). After every round, the agent updates completed items and next actions, creating a persistent record of automation progress. This is the same pattern followed by the `denis-gordeev.github.io` repository you are reading now.

### Connection to previous work

The autowork orchestrator represents the next step in Denis's progression from static NLP research toward interactive AI tooling:

| Phase | Projects |
|-------|----------|
| **Datasets and benchmarks** | RuREBus, NIED, RuNNE, SemEval submissions |
| **Fine-tuned models** | RuT5 keyword/topic generators, ruBERT rerankers |
| **AI infrastructure** | MCP-RUSSIA, RU-SKILL, RUSSIA.MD |
| **Automation and orchestration** | autowork, TG_SUMMARIZER |

The orchestrator ties together several earlier projects — MCP-RUSSIA provides the data layer, RU-SKILL provides the interaction patterns, and TG_SUMMARIZER demonstrates the kind of automated text processing that autowork now schedules and dispatches across an entire portfolio.

## codex-console-english: translating and fixing an OpenAI Codex console

The **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** repository is a fork of [dou-jiang/codex-console](https://github.com/dou-jiang/codex-console) (itself based on [cnlimiter/codex-manager](https://github.com/cnlimiter/codex-manager)). The original project is an integrated console for managing OpenAI Codex account registration, batch processing, token retrieval, and packaged execution — but it was written in Chinese and had broken compatibility with recent OpenAI registration flows.

Denis's fork applies the same localization pattern seen in his other projects (MCP-RUSSIA, RU-SKILL, RUSSIA.MD): taking an existing tool and adapting it for a broader, English-speaking audience. The key contributions of this fork include:

### Compatibility fixes

1. **Sentinel POW support** — OpenAI now enforces Sentinel POW validation; the fork adds an actual POW-solving flow instead of passing an empty value
2. **Separate registration and login flows** — registration no longer returns a usable token immediately, so the fork runs a separate login flow after registration
3. **Removed duplicate verification email sending** — the server already sends the email automatically, so the old manual resend could cause code conflicts
4. **Fixed re-login flow page handling** — updated login entry and password submission logic to match recent page flow changes
5. **Improved terminal and Web UI copy** — error and status messages made more readable

### Translation work

Denis translated the main web app surface, settings UI, task manager copy, and Outlook service/provider layers from Chinese to English. He also normalized user-facing success and error messages so tests and runtime behavior use consistent English, and migrated Pydantic response models from class-based `Config` to `ConfigDict`.

### Technical modernization

The fork replaces deprecated FastAPI `@app.on_event(...)` startup/shutdown hooks with a lifespan handler, adds regression tests for CPA upload URL normalization and DuckMail service wiring, and adds a test verifying that the app lifespan initializes shared runtime state on startup.

### Attribution note

The original project was created by [cnlimiter](https://github.com/cnlimiter) and further developed by [dou-jiang](https://github.com/dou-jiang). Denis's fork preserves the original structure and approach while applying compatibility fixes, flow updates, and English translations. The fork explicitly recommends crediting the upstream authors.

## My-RU-Coverage: continued growth

The **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** repository has grown from 77 to 83 commits since the last update. The project now contains 42 Russian company reports in `Pilot_Reports/`, 31 supply chain themes in `themes/`, and a full audit pipeline (`scripts/audit_ru_reports.py`). The MOEX-focused workflow includes dedicated scripts for blue chip queue management, report generation, financial data updates, and coverage status summaries — all tied together with the wikilink cross-referencing system described in previous posts.

## russia-md and ru-skill: ongoing maintenance

Both **[russia-md](https://github.com/denis-gordeev/russia-md)** and **[ru-skill](https://github.com/denis-gordeev/ru-skill)** were updated on May 23, 2026, indicating continued maintenance of the AI-friendly knowledge base and LLM skills ecosystem described in earlier posts.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
