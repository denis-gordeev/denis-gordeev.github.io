---
layout: post
title: "AUTOWORK: Denis Gordeev — from computational linguistics PhD to applied NLP at ecom.tech"
date: 2026-04-11
---

This post covers Denis Gordeev's professional trajectory and how his academic background in computational linguistics translates into production NLP systems at scale.

## Professional background

Denis Gordeev is a **Senior Data Scientist at ecom.tech** (part of the broader e-commerce technology ecosystem), where he applies NLP to real-world product search, recommendation, and content-processing challenges. He holds a **PhD in Applied and Computational Linguistics** from the **Moscow State Linguistic University**.

With over 11 years of experience building and deploying ML solutions and 12 years of software development, Denis bridges the gap between linguistic theory and engineering practice. His profile on Google Scholar lists his email at ecom.tech, confirming his current affiliation.

## Career arc

Denis's career has progressed through several roles that each combined research and engineering:

1. **Software Developer at AO "Гринатом"** — Early experience in enterprise software development, building production systems.
2. **NLP Group Lead at Russian Foreign Trade Academy (RVSD)** — Leading an NLP research group, likely working on the RuREBus shared task infrastructure and relation extraction for Russian business/government documents.
3. **NLP Team Lead at RANEPA** — Managing an NLP team at the Russian Presidential Academy of National Economy and Public Administration, where he published research on cross-linguistic semantic analysis and participated in SemEval evaluations.
4. **ML Initiatives Lead at Anecdote** — Transitioning into ML-focused leadership, bridging research prototypes and production systems.
5. **Senior Data Scientist at ecom.tech** — Current role, applying NLP at e-commerce scale.

This trajectory — from academic linguistics through research group leadership to industry-scale deployment — mirrors a broader pattern in the NLP community: researchers who build evaluation datasets and shared tasks (like RuREBus, RuNNE) later become the engineers building production search and recommendation systems.

## ecom.tech and applied NLP

While specific details of Denis's work at ecom.tech are not public, the company operates at the intersection of e-commerce and technology. Typical NLP challenges in this domain include:

- **Product search and retrieval** — Understanding user queries, handling synonyms and misspellings, ranking results by relevance.
- **Product categorization** — Automatically classifying items into hierarchical taxonomies from descriptions and titles.
- **Review analysis** — Extracting sentiment, aspects, and key themes from customer reviews at scale.
- **Content enrichment** — Augmenting product catalogs with structured attributes extracted from unstructured text.

The models Denis publishes on Hugging Face — rerankers for text search, keyword and topic generation models — align closely with these use cases. The bi-encoder/cross-encoder reranking pipeline, for instance, is a standard architecture for product search systems: a fast bi-encoder retrieves candidates from a large catalog, then a cross-encoder reranks the top results for quality.

## Publications as a foundation

Denis's academic publications provide theoretical grounding for this applied work:

- **RuREBus relation extraction dataset** (Dialogue 2020) — Relation extraction from business and government documents, directly relevant to extracting structured attributes from product descriptions.
- **RuNNE-2022 nested NER dataset** (Dialogue 2022) — Nested entity recognition, useful when product names contain other entities (e.g., "Apple MacBook Pro" contains both a brand and a product line).
- **NIED corpus** (JCDL 2025) — Numeric information extraction from dataset descriptions, applicable to extracting specifications and measurements from product catalogs.
- **SemEval-2021 Task 8 participation** — Measurement extraction from scientific text using transformers, demonstrating experience with the same extraction patterns needed for e-commerce structured data.

## Open-source engagement

Beyond publications, Denis maintains an active GitHub presence with repositories spanning configuration tooling (`config`), text processing utilities (`swendle`), and the NLP Party collection on Hugging Face. His Stack Overflow profile (464 reputation, 12 answers) reflects ongoing engagement with the broader developer community.

---

Professional profile: [`getprog.ai/profile/5531431`](https://www.getprog.ai/profile/5531431) · Research: [`Google Scholar`](https://scholar.google.com/citations?user=GGyyB6QAAAAJ&hl=en)
Models and datasets: [`huggingface.co/denis-gordeev`](https://huggingface.co/denis-gordeev)
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party)
