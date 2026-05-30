---
title: "AUTOWORK - BirdCLEF group temperatures boost F1, Divine Divinity RPG systems, tg_summarizer bug fixes, ru-skill legacy coverage"
date: 2026-05-30
layout: post
---

Four repositories saw significant new activity since yesterday's post. The **birdclef_2026** competition workspace is converging on group-specific temperature tuning for a substantial F1 gain, **open-divine-divinity-rust-bevy** has expanded into a full RPG with dialog rewards and weather, **tg_summarizer** fixed a critical dedup bug and a Lambda deadlock, and **ru-skill** completed legacy skill documentation coverage. Meanwhile, **My-RU-Coverage** and **codex-console-english** continue their respective localization and verification runs.

## BirdCLEF 2026: group-specific temperatures

The **[birdclef_2026](https://github.com/denis-gordeev/birdclef_2026)** workspace is a CPU-only code-competition entry for Kaggle's BirdCLEF 2026 challenge. Six notebooks (020–025) were added or updated across May 29–30.

### Notebook 022: group-specific temperature + threshold

The standout result: setting per-taxon-group temperatures during post-processing yields **+0.062 MicroF1** over uniform T=5. Aves benefits from a higher temperature (T=10–20), while Insecta and Amphibia prefer T=1–2, and Reptilia T=1. LOO cross-validation confirms a **+0.060 MicroF1** improvement. This has been integrated into the baseline submission notebook.

### Negative results

Several avenues were explored and deprioritized:

- **020 zero-shot**: all 28 missing species are non-Aves with no genus-mates in `train_audio`; Perch embeddings can't detect them; frequency floor hurts by −0.14 F1.
- **021 soundscape-only**: insect sonotypes get identical OOF scores with and without Perch priors — Perch adds zero signal for these species.
- **023 postprocessing v3**: grouped thresholding ≈ uniform T=4, no improvement over T=5.
- **024 insect spectral features**: worse than Perch baseline.
- **009 temporal (GRU/TCN)**: AUC drops to 0.772/0.758 vs 0.803 — overfits on 59 files.

### 025 window aggregation (May 30)

The latest notebook tests AUC-preserving transforms and max-over-windows aggregation. Result: max is already optimal, no further gain from window-level processing.

## open-divine-divinity-rust-bevy: full RPG systems

Two large commits on May 29 expanded the **[Rust + Bevy recreation](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** inspired by Divine Divinity.

### Audio, NPC schedules, item comparison, area transitions, rest

The first commit (161→161 tests) adds:

- **Audio system**: 34 game sounds across 6 categories with volume controls and cooldown
- **NPC day/night schedules**: `DayOnly`/`NightOnly` visibility toggling with combat log notifications
- **Item comparison**: stat differences shown on equip with upgrade detection
- **Area transitions**: markers for Castle Stormfist, Catacombs, and Rivertown
- **Rest mechanic**: hay bales advance the day/night cycle by 8 hours

### Dialog rewards, weather, status effects

The second commit (161→205 tests) adds:

- **Dialog rewards**: NPC choices now grant XP, gold, and items (e.g., Aleroth Healer gives Health Potion, Zandalor grants XP/gold for lore about the Marked Ones)
- **Weather system**: Rain, Snow, Fog with Light/Moderate/Heavy intensity — affects visibility, movement speed, enemy detection, and mana regen
- **Status effects**: Poison (DOT), Freeze (slow), Bleed, Weaken with tick-based processing and combined modifiers

## tg_summarizer: dedup and deadlock fixes

Two commits on May 29 addressed critical bugs in the **[Telegram summarizer](https://github.com/denis-gordeev/tg_summarizer)**:

- **Critical dedup bug fix**: Russian-response deduplication was broken, producing duplicate summaries. Also reduced `max_tokens` from 16K→4K and truncated update match context.
- **Lambda deadlock fix**: `_run_async_with_loop` silently returned `[]` when called from the same event loop (common in Lambda). Now uses a background thread. Also added SSM Parameter Store secret resolution, merged duplicate fetch/save functions, and bumped Lambda memory to 1024 MB. 61 total tests.

## ru-skill: legacy documentation coverage

Two commits on May 29 completed the **[ru-skill](https://github.com/denis-gordeev/ru-skill)** documentation regression suite:

- Fixed legacy-as-operational-default copy, expanded doc-regression for legacy skills with boundary notes and workflow/content assertions.
- Added workflow/content assertions for the remaining legacy skills (kakaotalk-mac, daiso-product-search, delivery-tracking). Doc-regression now covers all 13 target skills and all legacy skills — no uncovered legacy SKILL.md workflow remains.

## My-RU-Coverage: continued localization

A May-30 commit continued the **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** localization sweep:

- Fixed викалинк→викилинк typo, added Russian explanations for IPO/B2B/B2C/BaaS/DRaaS
- Replaced English-origin Russian terms: мерчанты→продавцы, селлеры→продавцы, фулфилмент→комплектация заказов, вендоры→производители, трейдинг→торговля
- Localized антифрод/комплаенс/скоринг, russified script comments and profiles
- 31 files changed across reports, scripts, network graph, and wikilink index

## codex-console-english: round 20

Round 20 of the English translation verification scan on May 30 confirmed no non-English text remains. All 29 tests pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
