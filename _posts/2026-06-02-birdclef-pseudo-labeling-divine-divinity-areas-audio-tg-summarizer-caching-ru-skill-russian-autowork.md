---
title: "AUTOWORK - BirdCLEF pseudo-labeling & ensemble stacking, Divine Divinity area transitions & audio playback, tg_summarizer caching, ru-skill heading normalization"
date: 2026-06-02
layout: post
---

The BirdCLEF 2026 competition workspace accelerates with pseudo-labeling and ensemble stacking notebooks, plus a critical soundscape label-construction fix. **open-divine-divinity-rust-bevy** ships full area transitions and actual audio playback. **tg_summarizer** gains S3 and history caching plus async fixes. **ru-skill** normalizes all headings to a canonical Russian scheme. **mcp-russia** connects real Open-Meteo and EGRUL APIs, while **My-RU-Coverage** replaces "девелопер" with "застройщик" and adds MOEX sector indexes.

## BirdCLEF 2026: pseudo-labeling, ensemble stacking, label fix

Six commits on **[birdclef_2026](https://github.com/denis-gordeev/birdclef_2026)** since the last round's post (which didn't cover this repo).

### 026 pseudo-labeling v2 and 027 OOF analysis

Notebook 026 explores pseudo-labeling: generating soft labels from the trained model for unlabeled soundscape data and retraining. Notebook 027 analyzes out-of-fold predictions by AUC — the key finding is that **LOO fusion hurts on oof_base**, meaning simple model averaging outperforms leave-one-out ensembling for this dataset.

### 029 pseudo-labeling v3 and 030 ensemble stacking

Notebook 029 (1,026 lines) implements a refined pseudo-labeling pipeline with per-sample R2 loss. Notebook 030 (868 lines) attempts ensemble stacking of multiple checkpoints. Both required several hotfixes:

- **Label construction bug**: soundscape labels were being constructed incorrectly, producing misaligned training targets
- **Focal padding bug**: zero-padding in focal extraction was leaking into feature computation
- **Syntax errors**: `np.float32` typo and double parenthesis in focal extraction

### Kaggle timeout and next steps

The 029 notebook timed out on Kaggle at the 9-hour mark. The TODO notes a need for a split approach to the embedding cache to fit within time limits.

## open-divine-divinity-rust-bevy: area transitions and audio playback

Two substantial commits on **[Rust + Bevy Divine Divinity](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)**.

### Actual audio playback (985 additions)

A new `audio_playback.rs` module (965 lines) replaces the stubbed audio system with real playback using Bevy's audio sink, including procedural placeholder sounds as fallback when asset files are missing.

### Full area transitions (815 additions)

The second commit implements complete area transitions between game regions:

- **Catacombs**: multi-level dungeon with darkness mechanics
- **Castle Stormfist**: fortified interior with guard patrols
- **Rivertown**: open hub area connecting to other regions

The `layout.rs` module grew by 500 lines to support the new zone definitions, spawn points, and transition markers. Save/load was updated to persist the current area.

## tg_summarizer: caching, async fixes, and robustness

Two commits improved the **[Telegram summarizer](https://github.com/denis-gordeev/tg_summarizer)**.

### AsyncOpenAI event loop fix + SSM caching (225 changes)

- **Event loop blocking**: `AsyncOpenAI` was being called from within an existing event loop (common in Lambda), causing a deadlock. Now resolved with proper async handling.
- **SSM client caching**: avoids re-creating the boto3 SSM client on every invocation.
- **Message ID preservation**: `message_id` is now correctly preserved in update operations.
- **Coverage check dedup**: removed duplicate coverage verification logic.

### S3 and history caching (303 changes)

- **S3 client caching**: singleton boto3 S3 client per Lambda container reuse.
- **History caching**: `HistoryManager` now caches recent fetches, reducing S3 reads.
- **Deadline during iteration**: summarization loop respects a configurable deadline to avoid Lambda timeouts.
- **None-safe text**: message text fields now handle `None` gracefully.

## ru-skill: heading normalization to Russian

Four commits on **[ru-skill](https://github.com/denis-gordeev/ru-skill)** continued the documentation cleanup:

- **Canonical heading scheme** (381 changes): all SKILL.md and docs/ headings normalized to a consistent Russian scheme. Chinese character artifacts (from earlier Korean skill imports) eliminated across 48 files.
- **Setup normalization**: `k-skill-setup/SKILL.md` and `packages/zoon-nearby/SKILL.md` cleaned up.
- **English headings → Russian**: translated remaining English headings and the last Korean doc fragments.
- **TODO governance tightened**: clearer tracking of remaining normalization work.

## mcp-russia: real API connections

A June 1 commit (872 additions, 240 deletions) in **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** connects previously stubbed endpoints to live data sources:

- **Open-Meteo weather API**: `rosgidromet` module now fetches real meteorological data (temperature, humidity, wind, pressure) for Russian cities
- **EGRUL API**: `fns` module queries the Federal Tax Service registry for legal entity information (ИНН, ОГРН, registration date, director)
- **Example files renamed**: Portuguese filenames → Russian (`analise-legislativa.md` → `analiz-zakonodatelstva.md`, `panorama-economico.md` → `ekonomicheskaya-panorama.md`, etc.)

## My-RU-Coverage: застройщик and MOEX indexes

A June 2 commit in **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** continues the russification sweep:

- **девелопер → застройщик**: replaced in 4 reports (EUTR, DOMRF, NLMK, ETLN)
- **Unified METRIC_LABELS dict** in `update_financials.py` — eliminates duplicate metric name definitions
- **7 MOEX sector indexes** added to the financial data pipeline

## codex-console-english: round 22

Round 22 of the translation verification scan on June 2: all 29 tests pass. No non-English text remains.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
