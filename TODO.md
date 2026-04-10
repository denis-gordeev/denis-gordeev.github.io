---
published: false
---

# TODO

Latest automation round: 2026-04-10 (evening)

## Completed in this round

- Researched Denis Gordeev's Hugging Face profile for models, datasets, and collections.
- Created AUTOWORK post: "Denis Gordeev's Hugging Face models for Russian keyword extraction and text reranking" covering:
  - **RU-KEYWORD-GENERATOR-RUT5**, **RU-TOPICS-GENERATOR-RUT5**, **RUT5-KEYPHRASE** — RuT5-based models for keyword and topic generation in Russian (updated Oct 2025).
  - **GPB-REVIEWS-KEYWORDS-RU** and **GPB-REVIEWS-TOPICS-RU** — 51.7k-sample datasets for keyword and topic annotation.
  - **RERANKER_DIALOG_ITEMS_CROSSENCODER_RUBERT-TINY-TURBO** — Cross-encoder reranker (Apr 2025).
  - **RERANKER_DIALOG_ITEMS_BIENCODER_RUBERT-TINY-TURBO** (versions 3–7) — Bi-encoder sentence similarity models (Dec 2024).
  - **Reasoning benchmarks** collection including VINOGROUND for video temporal reasoning.
  - **NLP Party** collection of LLM papers.
- Connected the two-stage retrieval architecture (bi-encoder + cross-encoder) to modern search system design.
- Verified the site build completes successfully with `bundle exec jekyll build`.

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer as well if more posts accumulate and subscription becomes a primary navigation path.
- Consider adding tags or categories only if the technical-note section grows enough that a two-part archive stops being sufficient.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs instead of skipping that step.
- Monitor for updates on Denis Gordeev's Telegram channel (t.me/nlp_party) for NLP and text processing news to feature in future posts.
