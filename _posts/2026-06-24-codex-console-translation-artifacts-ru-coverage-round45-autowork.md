---
title: "AUTOWORK - codex-console-english: ~60 translation artifact fixes; My-RU-Coverage: round #45 russification — 11 loanword categories across 10 reports"
date: 2026-06-24
layout: post
---

**[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** lands a large translation-quality pass fixing ~60 artifacts across 31 files. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** completes round #45 of its russification campaign, replacing 11 categories of loanwords across 10+ analyst reports.

## codex-console-english: ~60 translation artifact fixes

One commit (31 files, 121 insertions, 99 deletions) systematically cleans up translation artifacts left by the project's Chinese-to-English conversion. The fixes fall into four categories:

### Noun + "failed" → "Failed to" verb

The most pervasive pattern: Chinese noun-first error messages were literally translated as `"Startup failed"`, `"Cancellation failed"`, `"Registration failed"`. English idiom requires the verb-first form: `"Failed to start"`, `"Failed to cancel"`, `"Failed to register"`. This fix spans the JavaScript frontend (`app.js`, `accounts.js`, `email_services.js`) and Python backend (`constants.py`, `register.py`, `routes`).

### Redundant "successfully"

Over a dozen log lines and API responses said `"retrieved successfully"`, `"fetched successfully"`, `"refreshed successfully"`, `"completed successfully"`. In English, the success is implied by the verb itself — the redundant adverb was removed throughout (`dynamic_proxy.py`, `register.py`, `accounts.py`, `token_refresh.py`, `service.py`).

### Stilted UI labels and docstrings

- `"User information generation"` → `"User profile generation"`
- `"Operation timeout"` → `"Operation timed out"` (complete verb phrase)
- `"global configuration will be used"` → `"global settings will be used"` (natural UI phrasing)
- `"No available email service configuration found"` → `"No available email service found"`

### Chinese calques

Literal translations from Chinese that read unnaturally in English were rephrased — e.g. passive constructions and over-precise noun phrases simplified to idiomatic equivalents.

---

## My-RU-Coverage: Round #45 — 11 loanword categories replaced

One commit (31 files, 209 insertions, 166 deletions) continues the systematic replacement of English loanwords in Russian-language financial analyst reports.

### Key replacements

| Loanword | Russian replacement | Occurrences | Reports affected |
|----------|-------------------|-------------|-----------------|
| бизнес | предприятие / направление / деятельность | 19 | 10 |
| брокер | посредник | 6 | 3 |
| софт | программное обеспечение | — | — |
| кластер | узел / комплекс | — | — |
| трафик | поток посетителей | — | — |
| контент | информационное наполнение | — | — |
| медиа | информационно-развлекательные сервисы | — | — |
| спрэд | устранён | — | — |
| интегратор | поставщик комплексных решений | — | — |
| профучастники | профессиональные участники рынка | — | — |
| клиринг | removed as MOEX gloss | — | — |

Also fixed: missed *Логистические* in ALRS report.

### Tooling updates

- `discover.py`: *wikilink* → *викилинк*; `WIKILINK_ALIASES` expanded by 12 entries
- `build_themes.py`: russified (variable names and comments)
- Enrichment JSON: 6 corrections
- Network graph artifacts rebuilt

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
