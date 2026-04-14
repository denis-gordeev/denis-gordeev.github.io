---
title: "AUTOWORK - Denis Gordeev and the LIORI team at SemEval: a systematic push into multilingual NLP competitions"
date: 2026-04-14
layout: post
---

Denis Gordeev has been a recurring participant in the SemEval (Semantic Evaluation) shared tasks — a series of international competitions that benchmark NLP systems on specific language understanding problems. Between 2020 and 2021, Gordeev and colleagues from the **LIORI** team (based at the Russian Presidential Academy of National Economy and Public Administration — RANEPA) submitted solutions across five distinct tasks, progressively moving from single-language challenges to multilingual and multimodal setups.

## SemEval-2020 Task 10: Emphasis selection for written text in visual media

The [randomseed19](https://aclanthology.org/2020.semeval-1.74/) submission tackled the problem of **selecting the most visually salient words** in a piece of text for overlay on an image — a task relevant to meme generation, poster design, and visual storytelling. The system needed to identify which words in a sentence carry the most semantic weight when presented visually.

Gordeev's team approached this as a ranking problem, training models to predict human-annotated emphasis scores. The task drew connections between NLP and visual design, and the team's solution contributed to the broader discussion on how language models can inform computer vision workflows.

## SemEval-2020 Task 6: Definition extraction with the Gorynych Transformer

The [Gorynych Transformer](https://aclanthology.org/2020.semeval-1.73/) team addressed the automatic extraction of definitions from text — identifying definitional sentences and the terms they define. This is a foundational task for knowledge base construction, dictionary building, and educational technology.

The team deployed a multi-task learning architecture that jointly predicted definition boundaries and term-definendum pairs, leveraging transformer-based encoders to capture the semantic relationship between a definition and the concept it explains. The approach demonstrated that joint multi-task modeling outperforms pipeline-based extraction on this task.

## SemEval-2020 Task 8: Causality in financial texts (FinCausal)

The [LIORI submission to FinCausal 2020](https://aclanthology.org/2020.semeval-1.116/) targeted causal relation extraction in financial documents — identifying sentences that express cause-effect relationships in earnings reports, market analyses, and economic news. Financial causality is critical for automated market analysis, risk assessment, and investment research tooling.

The team's system combined transformer-based classification with careful feature engineering on financial text structures. This work foreshadows Gordeev's later interest in automated equity research, visible in his **MY-RU-COVERAGE** project for Moscow Exchange ticker analysis.

## SemEval-2021 Task 2: Word-in-context disambiguation

The [SemEval-2021 Task 2](https://aclanthology.org/2021.semeval-1.177/) submission addressed lexical semantic change detection — determining whether a word's meaning shifts between different contexts or time periods. The team explored both span prediction and binary classification approaches, treating word-in-context disambiguation as a dual problem of boundary detection and sense classification.

This work is directly relevant to building robust NLP pipelines that handle semantic drift, a challenge particularly acute for low-resource languages where training data spans limited time periods.

## SemEval-2021 Task 8: Table-to-text and measurement extraction

The [SemEval-2021 Task 8](https://aclanthology.org/2021.semeval-1.232/) system ("Ask transformer for measurements") focused on extracting structured measurements from tabular data and generating natural language descriptions — a bidirectional task requiring both information extraction and natural language generation. The team's transformer-based solution handled the full pipeline from table parsing to measurement entity identification to text realization.

This task sits at the intersection of structured data understanding and text generation, two capabilities that are central to modern LLM-based research automation tools.

## The LIORI research program: a decade of competition-driven NLP

Viewed together, these SemEval submissions trace a coherent research trajectory:

| Year | Task | Core Problem | Approach |
|------|------|-------------|----------|
| 2020 | Task 10 | Emphasis selection | Ranking models for visual-textual salience |
| 2020 | Task 6 | Definition extraction | Multi-task transformer learning |
| 2020 | Task 8 | Financial causality | Transformer classification + feature engineering |
| 2021 | Task 2 | Word-in-context | Span prediction + binary classification |
| 2021 | Task 8 | Table-to-text | End-to-end transformer pipeline |

The LIORI team's participation pattern shows a deliberate progression from single-task solutions (emphasis selection, definition extraction) to more complex multistep problems (table-to-text, financial causality), with each competition informing the next. This competition-driven research model has been a productive strategy for the Russian NLP community more broadly, producing datasets like **RuREBus** and **RuNNE** that are now standard benchmarks for Russian-language NLP.

## From competition submissions to production tooling

Many of the techniques developed for these SemEval tasks have direct analogs in Gordeev's later production work:
- **Definition extraction** (Task 6) → knowledge base construction for **RUSSIA.MD**
- **Financial causality** (Task 8) → equity research automation in **MY-RU-COVERAGE**
- **Table-to-text** (Task 8) → structured report generation in the AUTOWORK pipeline
- **Word-in-context** (Task 2) → robust text understanding for **TG_SUMMARIZER** filtering

The SemEval track record demonstrates a research philosophy where competition problems serve as proving grounds for techniques that later migrate into practical tooling — a pattern that continues in Gordeev's current work on MCP servers and LLM skills for Russian-language AI workflows.
