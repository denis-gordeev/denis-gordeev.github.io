---
layout: post
title: "AUTOWORK: Denis Gordeev's local-first AI orchestrator and a decade of NLP research"
date: 2026-04-12
---

This post highlights two things that don't usually appear together in a single update: Denis Gordeev's **AUTOWORK** orchestrator — a local-first tool for automating repository maintenance with AI agents — and his long-standing academic footprint in computational linguistics, which now totals **195 citations** on Google Scholar.

## AUTOWORK: AI agents that maintain your repositories

The **[AUTOWORK](https://github.com/denis-gordeev/autowork)** project is a local-first orchestrator for managing a folder of git repositories. Instead of relying on cloud-based CI/CD bots, AUTOWORK runs AI agents (via `codex exec` or similar tools) directly on your machine, on a schedule.

### How it works

Each managed repository receives an `autowork.sh` script, a cron schedule, and optional Telegram integration for status notifications. The orchestrator follows a clear priority order when deciding what to work on:

1. **`AUTOWORK_INSTRUCTIONS.md`** — repository-specific automation directives.
2. **Open issues and PRs/MRs** — real work items from the forge.
3. **TODOs from `README.md` or `TODO.md`** — persistent task lists.

Agents are expected to maintain a living task list, update it after each round, and run relevant checks (builds, linters, tests) before committing.

### Why local-first matters

Local-first orchestration addresses several practical concerns:

- **Privacy**: No code or prompts leave your machine unless you configure them to.
- **Cost control**: You bring your own AI API keys and decide when to spend tokens.
- **Repo-level autonomy**: Each repository has its own instructions, schedule, and Telegram topic — no central dashboard needed.
- **Offline resilience**: Crontab-based scheduling means automation continues even when cloud services are unreachable.

The project is written in **Python (99%)** with a lightweight shell wrapper. It includes CLI commands for repository discovery (`run`), single-repo execution (`project-run`), code review (`review`), crontab synchronization (`sync-crontab`), and Telegram forum-topic mirroring (`telegram-sync`).

This is the same engine that produces the AUTOWORK posts on this blog.

## TG_SUMMARIZER: 6 stars and counting

The **[TG_SUMMARIZER](https://github.com/denis-gordeev/tg_summarizer)** project — an automated tool for collecting, filtering, and summarizing Telegram channel messages using OpenAI GPT — recently crossed **6 stars** and accumulated **61 commits**.

Key capabilities include:

- **AI-based message filtering** with NLP/ML focus.
- **Digest generation** with HTML links and message deduplication.
- **Group summaries** — a single overview of all channels in a batch.
- **Automatic history restoration** from the target channel if local JSON is missing or corrupted.
- **Docker support** — build and run with the provided `Dockerfile`.

The tool is built for the Russian-speaking tech community, where Telegram is the primary platform for technical channels, group discussions, and industry news. It requires Python 3.8+, Telegram API credentials, and an OpenAI API key.

## A decade of NLP research: 195 citations, h-index 9

Denis's Google Scholar profile ([scholar.google.com](https://scholar.google.com/citations?user=GGyyB6QAAAAJ)) reflects a research trajectory starting in **2015** with work on aggression detection in online communities and continuing through **2022** with papers on meme generation and regional internet communication.

### Most-cited work

| Paper | Year | Citations |
|---|---|---|
| Detecting state of aggression in sentences using CNN | 2016 | 38 |
| BERT of all trades, master of some | 2020 | 19 |
| Relation extraction dataset for the Russian language | 2020 | 17 |
| Automatic detection of verbal aggression for Russian and American imageboards | 2016 | 16 |
| LIORI at SemEval-2021 task 8: Ask transformer for measurements | 2021 | 11 |

### Research interests

Computational Linguistics, Natural Language Processing, Named Entity Recognition, Relation Extraction, Aggression/Toxicity Detection, and Semantic Evaluation.

The citation trend peaked between 2020–2023, with 127 of the 195 total citations accumulated since 2021 — indicating that Denis's more recent work (BERT-based models, SemEval shared tasks, and Russian-language NLP datasets) has had the most impact.

## Connecting research to practice

The through-line from Denis's academic work to his current tooling is clear:

1. **Datasets and annotations** (RuREBus, NIED, RuNNE, GPB Reviews) → structured data for training Russian-language NLP models.
2. **Fine-tuned models on Hugging Face** (RuT5 keyword/topic generators, ruBERT rerankers) → reusable components for text understanding.
3. **Applied tools** (TG_SUMMARIZER, AUTOWORK) → end-user products that leverage those models.
4. **AI infrastructure** (MCP-RUSSIA, RU-SKILL, RUSSIA.MD) → the layer that connects LLMs to localized data sources and tool workflows.

The academic foundation gives Denis's practical tools a quality that purely engineering-driven projects often lack: **grounding in established NLP methodology**. Keyword extraction, topic generation, and text reranking aren't just API calls to an LLM — they're tasks Denis has published peer-reviewed papers on.

---

Explore the repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Models and datasets: [`huggingface.co/denis-gordeev`](https://huggingface.co/denis-gordeev).
Academic profile: [`scholar.google.com`](https://scholar.google.com/citations?user=GGyyB6QAAAAJ).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
