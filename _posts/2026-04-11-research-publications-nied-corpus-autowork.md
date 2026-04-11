---
layout: post
title: "AUTOWORK: Denis Gordeev's research publications — NIED corpus and nested text labeling"
date: 2026-04-11
---

This post covers Denis Gordeev's academic research publications and papers currently under review, focusing on structured information extraction and text annotation infrastructure.

## NIED: A Corpus for Numeric Information Extraction from Dataset Descriptions

Denis Gordeev co-authored the **NIED** corpus, published at the **2025 ACM/IEEE Joint Conference on Digital Libraries (JCDL 2025)**. The paper introduces an annotated collection of 3,926 dataset descriptions drawn from scientific papers and repositories.

The key contribution is a **two-tier labeling scheme** that separates different levels of numeric information mentioned in dataset documentation. This approach addresses a practical problem: dataset descriptions often contain measurements, statistics, and quantitative claims scattered across unstructured text, making it difficult for automated systems to extract structured metadata.

The work builds on earlier efforts in measurement extraction, including Denis's participation in **SemEval-2021 Task 8** ("LIORI at SemEval-2021 Task 8: Ask Transformer for measurements"), where his team tackled the related challenge of extracting scientific measurements from text using transformer-based models.

## Nested text labeling structures (under review at ICLR 2026)

A more recent paper, **"Nested Text Labelling Structures to Organize Information Extraction"**, is under review at **ICLR 2026**. The authors — Denis Gordeev, Adis Davletov, Alexey Rey, Galiya Akzhigitova, and Georgiy Geymbukh — propose a structural approach to organizing nested annotations in text.

The core idea addresses a common bottleneck in NLP pipelines: when a single text span needs multiple overlapping labels (e.g., a phrase that is simultaneously a named entity, part of a relation, and within a larger discourse unit), traditional flat annotation schemes force arbitrary choices about which label takes precedence. Nested labeling structures allow these overlaps to be represented explicitly, enabling downstream models to learn from the full annotation context rather than a flattened projection.

This connects directly to the practical annotation tools Denis has released on Hugging Face, such as the RuT5-based keyword and topic generation models, which can serve as components within a broader nested annotation pipeline.

## Semantic and cross-linguistic research

Earlier work includes a comparative analysis of the semantic field of "deception" across Russian and American online communication, published through RANEPA (Russian Presidential Academy of National Economy and Public Administration), where Denis is affiliated as a researcher in computational linguistics. This study used imageboard message corpora to examine how deceptive language manifests differently across cultural and linguistic communities — relevant groundwork for modern LLM safety and alignment research.

## Research trajectory

Taken together, Denis's publications trace a coherent arc:

1. **Semantic analysis** — understanding how meaning varies across languages and communities.
2. **Annotation infrastructure** — building datasets (RURED, RURED2, NIED, GPB-reviews) that make Russian NLP practical and reproducible.
3. **Structured extraction** — developing models and labeling schemes that turn unstructured text into machine-readable formats.
4. **LLM-era tooling** — recent repositories (RU-SKILL, TG_SUMMARIZER, MCP-RUSSIA) applying these foundations to production LLM workflows.

---

Explore the publications and datasets at [`huggingface.co/denis-gordeev`](https://huggingface.co/denis-gordeev).
Shorter updates and links continue at [`t.me/nlp_party`](https://t.me/nlp_party).
