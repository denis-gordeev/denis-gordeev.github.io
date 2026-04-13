---
title: "AUTOWORK - Denis Gordeev's AI infrastructure push: MCP-RUSSIA, RU-SKILL, and equity research automation"
date: 2026-04-13
layout: post
---

Denis Gordeev has been active on a new front: building AI infrastructure and automated research tooling for Russian-speaking users and developers. His recent repositories reveal a systematic effort to localize LLM tooling, create MCP (Model Context Protocol) servers for Russian public data sources, and automate equity research on the Moscow Exchange.

## MCP-RUSSIA: Localizing AI tooling for Russian data sources

The **MCP-RUSSIA** repository (updated April 12, 2026, 131 commits) represents Gordeev's work on adapting the Model Context Protocol for Russian-language use cases. MCP has emerged as a standard for connecting AI assistants to external data sources, and this project migrates the architecture from a Brazilian predecessor to serve Russian public and government APIs.

The repository follows a strict `package-by-feature` structure, with each feature encapsulating HTTP clients, MCP tools, schemas, resources, and prompts, all registered via FastMCP. The project is built with a modern Python stack using `uv`, `pytest`, `ruff`, and `mypy`, with a Makefile-based developer toolchain.

Key aspects of the migration:
- Replacing Brazilian data sources with Russian public/state APIs
- Localizing tools and prompts to Russian language
- Maintaining backward compatibility while systematically transitioning content
- Strict modular architecture with isolated feature packages

The repository is currently in a work-in-progress migration state, with issues disabled and contributions accepted only via pull requests.

## RU-SKILL: LLM skills for Russian-speaking users

Alongside MCP-RUSSIA, the **RU-SKILL** repository (96 commits) focuses on creating a collection of LLM skills adapted for Russian and Russian-speaking use cases. The project is transitioning from legacy Korean service integrations toward Russian-focused scenarios.

The guiding principles prioritize public and free APIs, adding proxies only when necessary, and centralizing documentation and automation. The repository includes legacy tools for SRT/KTX booking, Seoul subway navigation, KBO/K League results, KakaoTalk Mac CLI, HWP document conversion, local search, and delivery tracking—all being adapted or replaced with Russian equivalents.

Development is tracked via Pull Requests rather than a separate issue tracker, maintaining the same lightweight contribution model as MCP-RUSSIA.

## MY-RU-COVERAGE: Automated equity research for MOEX

Perhaps the most ambitious recent project is **MY-RU-COVERAGE** (77 commits), an equity research automation tool for Russian-listed companies. The repository uses interconnected Markdown reports via `[[wikilinks]]` to build a knowledge graph of companies, technologies, supply chains, and end markets on the Moscow Exchange.

The project is currently transitioning from a legacy Taiwanese corpus to focus primarily on MOEX tickers (`.ME` suffix). The structure includes:
- **Pilot_Reports/**: Company cards with business descriptions and supply chain positions
- **scripts/**: CLI tools for generation, financial updates, audits, and graph building
- **WIKILINKS.md**: Auto-generated entity index
- **network/**: Co-occurrence graphs of company relationships
- **themes/**: Supply chain maps for specific sectors

The Python-based CLI enables adding tickers, pulling and updating financials and valuations via `yfinance`, running quality audits, and rebuilding wikilink and network indices. Explicit examples include major Russian companies like **SBER** (Сбер), **GAZP** (Газпром), **DOMRF**, **AKRN**, and **AFLT**.

## The bigger picture: building AI infrastructure for Russian markets

These three repositories form a coherent ecosystem:
1. **MCP-RUSSIA** provides the data layer—connecting AI assistants to Russian public sources
2. **RU-SKILL** provides the interaction layer—LLM capabilities tailored to Russian workflows
3. **MY-RU-COVERAGE** demonstrates a concrete application—automated financial research powered by the infrastructure

This stack positions Gordeev as one of the few developers systematically building open-source AI infrastructure for the Russian market, complementing his earlier work on Russian-language NLP benchmarks and Hugging Face model deployments.

The repositories are all MIT-licensed and open to contributions via pull requests, though issues are disabled across the board in favor of a PR-driven development model.
