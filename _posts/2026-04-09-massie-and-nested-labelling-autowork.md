---
layout: post
title: "AUTOWORK: MASSIE at ACL 2025 and Nested Text Labelling at Dialogue 2025"
date: 2026-04-09
---

This automation round covers two recent publications co-authored by Denis Gordeev that appeared in 2025.

## MASSIE — A Massively Multilingual IE Benchmark (ACL 2025 Findings)

At **ACL 2025** (Findings), Denis Gordeev contributed to **MASSIE** (MAssively multilingual instruction-tuned Information Extraction), a large-scale benchmark for information extraction in over **95 languages**.

MASSIE standardises and unifies **215 manually annotated datasets** across **5 core IE tasks**:
named entity recognition, relation extraction, event extraction, and others.
The corpus is split into two tiers: **M-Heavy** (~17 M samples for final evaluation)
and **M-Light** (~2.3 M samples for iterative development).

The paper also introduces **LF1**, a structure-aware evaluation metric based on
Levenshtein distance that captures partial correctness of extraction outputs —
an improvement over the binary exact-match scores traditionally used in IE.

The empirical analysis reveals significant cross-lingual and cross-task performance
disparities among multilingual LLMs, and notably finds that language-specific
instructions and exemplars do not reliably improve results.

Paper: [Massively Multilingual Instruction-Following Information Extraction](https://aclanthology.org/2025.findings-acl.182/)

## Nested Text Labelling Structures (Dialogue 2025)

At the **Dialogue 2025** conference, Denis Gordeev presented work on **nested text
labelling structures** for organising knowledge in AI systems. The paper proposes a
framework of **three nested data models**, each distinguished by its level of
complexity, ranging from flat relational representations to richer nested structures
that can capture overlapping and hierarchical annotations.

This work is particularly relevant for tasks like **RuSentNE** — opinion-oriented
named entity recognition in Russian news texts — where entities can carry multiple,
overlapping sentiment labels. The accompanying **[rured2](https://github.com/denis-gordeev/rured2)**
repository provides tools for working with these nested annotation formats.

Paper: [Nested Text Labelling Structures to Organize Knowledge in AI](https://openreview.net/forum?id=PxYlYQ6orQ)

Both publications reflect the ongoing effort to make information extraction more
robust, multilingual, and capable of handling the structural complexity of real-world
text annotations.
