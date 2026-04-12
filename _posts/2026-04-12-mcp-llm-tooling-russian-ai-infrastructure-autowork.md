---
layout: post
title: "AUTOWORK: Denis Gordeev builds MCP servers and LLM skills for Russian-language AI workflows"
date: 2026-04-12
---

This post covers Denis Gordeev's recent shift toward applied LLM integration, AI agents, and the Model Context Protocol (MCP) — with a strong emphasis on the Russian-speaking tech ecosystem.

## From NLP models to AI agents

Denis's earlier work on Hugging Face focused on Russian-language NLP infrastructure: keyword generators, topic models, rerankers, and evaluation datasets. His recent GitHub activity reveals a pivot toward **connecting LLMs to local tools and data sources** via the Model Context Protocol.

MCP, introduced by Anthropic in late 2024, has become a standard for giving LLMs structured access to external systems — file systems, databases, APIs, and development tools. But localized MCP servers that understand regional context, language, and data sources remain scarce. Denis is filling that gap for Russian-speaking users.

## MCP-RUSSIA: Localized model context protocol servers

The **[MCP-RUSSIA](https://github.com/denis-gordeev/mcp-russia)** repository provides MCP servers configured specifically for residents of Russia and Russian-speaking users. The project addresses a practical need: most publicly available MCP servers assume English-language queries and Western data sources. MCP-RUSSIA bridges this by exposing contextually relevant servers that can answer questions about local services, regulations, geography, and infrastructure — all through the standardized MCP interface that modern LLM clients understand.

This work connects directly to Denis's earlier NLP research. The reranking models and keyword extraction pipelines he published on Hugging Face are the same building blocks that power high-quality tool retrieval and context understanding in an agentic workflow.

## RU-SKILL: LLM skills for Russian-speaking users

Alongside MCP servers, Denis released **[RU-SKILL](https://github.com/denis-gordeev/ru-skill)** — a set of LLM skills (structured prompt templates and tool configurations) tailored for Russian-language interactions. Skills in the LLM context are reusable patterns that teach a model how to accomplish specific tasks: searching information, formatting output, interacting with external tools, or following multi-step workflows.

RU-SKILL complements MCP-RUSSIA by providing the "how to use the tools" layer on top of the "what tools are available" layer that MCP servers expose. Together, they form a stack:

1. **MCP-RUSSIA** — defines what external systems and data sources the LLM can access.
2. **RU-SKILL** — defines structured workflows for using those tools effectively in Russian.

## AI-friendly knowledge bases: RUSSIA.MD and RUSSIA-MD

Two related projects provide structured, markdown-formatted knowledge about Russia:

- **[RUSSIA.MD](https://github.com/denis-gordeev/russia.md)** — A general knowledge base covering geography, culture, infrastructure, and practical information.
- **[RUSSIA-MD](https://github.com/denis-gordeev/russia-md)** — A closely related variant, likely with different scope or update cadence.

These knowledge bases are designed for **Retrieval-Augmented Generation (RAG)**: they provide clean, structured text that LLMs can retrieve from when answering questions, reducing hallucination and grounding responses in verified facts. The markdown format makes them easy to parse, update, and embed for semantic search.

## TG_SUMMARIZER: Telegram chat summarization

The **[TG_SUMMARIZER](https://github.com/denis-gordeev/tg_summarizer)** project applies NLP/LLM capabilities to automatically summarize Telegram conversations. This is a practical application of the keyword and topic generation models Denis published earlier on Hugging Face (RU-KEYWORD-GENERATOR-RUT5, RU-TOPICS-GENERATOR-RUT5), now packaged as an end-user tool.

Telegram is one of the most widely used messaging platforms in the Russian-speaking tech community, and chat summarization addresses a real pain point: keeping up with high-volume technical channels and group discussions.

## ROFI-MCP and MULTIMODAL-MCP-CLIENT: Voice-powered agentic workflows

Beyond text-based tools, Denis has been experimenting with multimodal MCP integrations:

- **[ROFI-MCP](https://github.com/denis-gordeev/rofi-mcp)** (June 2025) — Integrates the Rofi window switcher/launcher with MCP, enabling LLM-driven application launching and window management.
- **[MULTIMODAL-MCP-CLIENT](https://github.com/denis-gordeev/multimodal-mcp-client)** (February 2025) — A multi-modal MCP client built for voice-powered AI agentic workflows, combining speech recognition with tool-use capabilities.

These projects point toward a broader vision: LLMs that don't just process text, but interact with the user's desktop environment, handle voice input, and orchestrate multi-step workflows across applications.

## MY-RU-COVERAGE: Structured financial data with wiki-linking

The **[MY-RU-COVERAGE](https://github.com/denis-gordeev/my-ru-coverage)** repository (updated April 12, 2026) contains equity research coverage of Russia-listed companies, featuring business overviews, supply chain mapping, and financial data with wikilink cross-referencing. This is a structured knowledge base that could serve as context for financial analysis LLM workflows — another example of Denis building AI-ready data infrastructure.

## The bigger picture

Denis's recent work traces a clear arc from his academic and research background:

- **Annotation datasets (RuREBus, NIED, RuNNE)** → structured data that teaches models to extract information from text.
- **Fine-tuned models (RuT5 keyword/topic generators, ruBERT rerankers)** → practical NLP components for Russian-language pipelines.
- **MCP servers and LLM skills** → connecting those components to interactive AI agents that can access external tools and localized knowledge.

This progression — from static datasets to interactive agent infrastructure — mirrors the broader shift in the NLP community from model training to model deployment and integration.

---

Explore the repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Models and datasets: [`huggingface.co/denis-gordeev`](https://huggingface.co/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
