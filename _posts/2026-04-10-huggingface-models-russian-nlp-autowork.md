---
layout: post
title: "AUTOWORK: Denis Gordeev's Hugging Face models for Russian keyword extraction and text reranking"
date: 2026-04-10
---

This post covers the models, datasets, and collections Denis Gordeev maintains on Hugging Face, focusing on Russian-language NLP infrastructure.

## Keyword and topic generation models

Denis has published several fine-tuned RuT5 models (0.2B parameters) for automatic text annotation tasks in Russian:

- **RU-KEYWORD-GENERATOR-RUT5** — Generates keyword annotations for Russian texts. Trained to produce concise, domain-relevant keyphrases that capture the main topics of a document.
- **RU-TOPICS-GENERATOR-RUT5** — Produces higher-level topic labels rather than individual keywords, useful for document clustering and content summarization.
- **RUT5-KEYPHRASE** — A closely related keyphrase extraction model, also based on the RuT5 architecture.

These models were accompanied by two public datasets released in October 2025:

- **GPB-REVIEWS-KEYWORDS-RU** — 51.7k Russian text samples with keyword annotations, derived from customer reviews.
- **GPB-REVIEWS-TOPICS-RU** — The same corpus annotated with topic-level labels, providing training and evaluation data for topic modeling.

Together, these resources form a pipeline: raw Russian text can be processed through the keyword model for fine-grained tagging, then through the topic model for document-level categorization.

## Reranking and similarity models

A separate line of work focuses on text reranking and sentence similarity for Russian, using the compact ruBERT-tiny-turbo encoder (~29M parameters):

- **RERANKER_DIALOG_ITEMS_CROSSENCODER_RUBERT-TINY-TURBO** — A cross-encoder reranker (updated April 2025) that scores query-document pairs with high precision. Cross-encoders typically achieve better ranking quality than bi-encoders at the cost of slower inference.
- **RERANKER_DIALOG_ITEMS_BIENCODER_RUBERT-TINY-TURBO** (versions 3–7) — A series of bi-encoder models (updated December 2024) that embed queries and documents independently for efficient similarity search. The multiple versions likely reflect iterative training improvements and hyperparameter tuning.

The bi-encoder family is well-suited for first-stage retrieval over large corpora, while the cross-encoder serves as a precise reranker on top of initial candidates. This two-stage architecture — dense retrieval followed by cross-encoder reranking — is the standard pattern in modern search systems.

## Reasoning benchmarks collection

Denis also curates a **Reasoning benchmarks** collection on Hugging Face that tracks evaluation papers for LLM capabilities. One notable entry is:

- **VINOGROUND** — A benchmark for scrutinizing large multimodal models (LMMs) over dense temporal reasoning with short videos. This addresses an important gap: many LMM evaluations focus on static images, while video understanding requires reasoning about temporal relationships and event sequences.

## NLP Party collection

The broader **NLP Party** collection ([`huggingface.co/collections/denis-gordeev/nlp-party`](https://huggingface.co/collections/denis-gordeev/nlp-party)) gathers papers on model alignment, long-context reasoning, efficient architectures (such as Hyena-style long convolutions distilled from transformers), and interpretability in the era of large language models.

---

Explore the models and datasets at [`huggingface.co/denis-gordeev`](https://huggingface.co/denis-gordeev).
Shorter updates and links continue at [`t.me/nlp_party`](https://t.me/nlp_party).
