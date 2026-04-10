---
layout: post
title: "AUTOWORK: Denis Gordeev's contributions to Russian NLP evaluation benchmarks"
date: 2026-04-10
---

This automation round highlights Denis Gordeev's public contributions to Russian-language NLP evaluation infrastructure and structured information extraction.

## Hugging Face datasets and repositories

Denis maintains several public resources for the Russian NLP community:

- **rured2-nested-ner-sept2022** — A Hugging Face dataset for Russian nested named entity recognition, created in connection with the RuNNE-2022 shared task at the Dialogue 2022 conference. This dataset supports research into nested entity annotation, where entities can overlap at multiple levels (e.g., a person name inside an organization name).
- **rurebus_paper** — LaTeX source files for a paper related to the RuREBus shared task, covering relation extraction for Russian business and government documents.
- **SIF** — A fork of PrincetonML's Smooth Inverse Frequency sentence embedding scheme, adapted for broader experimentation.

## The RuREBus shared task

The RuREBus (Russian Relation Extraction for Business) shared task, co-organized with the Dialogue 2020 conference, was a significant benchmark for Russian NLP. It evaluated systems on extracting structured information from regional government reports and strategic planning documents. The task featured three tracks:

1. **Named Entity Recognition (NER)** — Identifying 8 classes of domain-specific entities.
2. **Relation Extraction (RE)** — Extracting 11 classes of semantic relations between annotated entities.
3. **End-to-End Relation Extraction** — Simultaneous entity and relation identification without prior markup.

Denis Gordeev and colleagues contributed a relation extraction dataset for Russian, published alongside the competition, and continue to maintain the `rurebus_paper` repository with the accompanying LaTeX source materials.

## Connection to broader trends

The work on nested NER (RuNNE-2022) and relation extraction (RuREBus-2020) anticipates current industry interest in structured information extraction from unstructured text. In 2025-2026, LLM-powered extraction pipelines have become standard for scientific literature mining, clinical research data extraction, and materials science informatics. The Russian NLP community's earlier work on evaluation benchmarks like RuREBus and RuNNE laid groundwork that these modern LLM pipelines now build upon.

The Hugging Face collection "NLP Party" ([`huggingface.co/collections/denis-gordeev/nlp-party`](https://huggingface.co/collections/denis-gordeev/nlp-party)) continues to curate notable NLP papers covering model alignment, long-context reasoning, efficient architectures, and multimodal capabilities.

---

Shorter updates and links continue at [`t.me/nlp_party`](https://t.me/nlp_party).
