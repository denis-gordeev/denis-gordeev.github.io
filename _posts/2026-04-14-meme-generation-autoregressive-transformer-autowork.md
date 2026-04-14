---
title: "AUTOWORK - Denis Gordeev on automatic meme generation with autoregressive transformers"
date: 2026-04-14
layout: post
---

Denis Gordeev has explored the creative intersection of NLP and computer vision through **automatic meme generation** — a task that requires understanding both linguistic structure and visual context to produce coherent, culturally relevant image-text combinations.

The 2022 publication, **"Automatic meme generation with an autoregressive transformer"** (co-authored with V. Potapov), represents an early foray into multimodal generative AI that predates the current wave of image-text models like DALL-E and Stable Diffusion.

## The meme generation problem

Automatic meme generation is deceptively complex. A successful meme requires:

- **Semantic alignment** between the image content and the overlaid text
- **Cultural relevance** — understanding of current internet discourse patterns
- **Linguistic creativity** — wordplay, irony, or unexpected juxtaposition
- **Visual composition** — text placement that complements rather than obscures the image

The task sits at the intersection of multiple NLP challenges: image captioning, humor generation, template filling, and tone matching. For Russian-language memes, the challenge is compounded by the need for morphologically aware text generation and culturally specific references.

## Autoregressive transformer approach

Gordeev and Potapov's approach leveraged an autoregressive transformer architecture to generate meme text conditioned on input images. The key insight was treating meme generation as a **conditional text generation problem** with visual grounding:

1. **Image encoding** — visual features extracted using a pretrained vision encoder
2. **Text conditioning** — the transformer generates token-by-token, attending to both the image representation and previously generated text
3. **Template awareness** — the model learns common meme structures (top text / bottom text patterns, reaction formats)
4. **Cultural embedding** — training on Russian-language internet content to capture discourse patterns specific to Runet

The autoregressive nature of the model allows for coherent multi-token generation while maintaining alignment with the visual input, a significant step up from template-filling or retrieval-based approaches.

## Why meme generation matters for NLP research

While meme generation might seem like a novelty task, it serves as a **stress test for multimodal understanding**:

- **Grounded language generation** — the model must produce text that is literally true of the image while also being culturally meaningful
- **Implicit reasoning** — good memes require understanding of causality, emotion, and social context that isn't explicitly present in the image
- **Low-resource challenge** — Russian-language meme datasets are smaller than English equivalents, requiring efficient learning from limited data
- **Evaluation difficulty** — automatic metrics (BLEU, ROUGE) poorly capture meme quality, highlighting the need for human-centered evaluation

These same challenges appear in more "serious" applications like automated report generation, visual question answering, and accessibility tooling (alt-text generation for images).

## Connection to broader research trajectory

The meme generation work connects to several themes in Gordeev's research:

| Area | Connection |
|------|------------|
| **SemEval emphasis selection** (2020) | Both tasks require identifying visually salient text — memes need the right words on the right images |
| **Multimodal toxicity detection** | Earlier work combining text and image analysis for content moderation |
| **TG_SUMMARIZER** | Both involve generating human-readable text from complex inputs (messages vs. images) |
| **MCP-RUSSIA** | Current work on Russian-localized AI tooling shares the cultural adaptation challenge |

The progression from meme generation to production MCP servers shows a consistent focus on **making AI systems that understand Russian internet culture** — whether that's generating content that resonates with Runet audiences or building infrastructure that respects Russian data sources and norms.

## The multimodal future

The 2022 meme generation paper anticipated the current shift toward multimodal AI systems. Today's large language models increasingly incorporate vision capabilities (GPT-4V, Claude, Gemini), and the challenges identified in the meme generation work — cultural grounding, visual-textual alignment, creative generation — remain active research areas.

For Russian-language NLP specifically, multimodal work is still relatively underexplored compared to text-only tasks. The meme generation research, combined with Gordeev's later work on aggression detection in image-text combinations and his current MCP infrastructure projects, traces a path from academic exploration to practical tooling that serves Russian-speaking AI users.

## Publication details

- **Title:** Automatic meme generation with an autoregressive transformer
- **Year:** 2022
- **Authors:** Denis Gordeev, V. Potapov
- **Available via:** Google Scholar (profile: GGyyB6QAAAAJ)

This work represents one of the more creative applications of transformer models in the Russian NLP space — a reminder that serious research doesn't always need to be serious in subject matter.
