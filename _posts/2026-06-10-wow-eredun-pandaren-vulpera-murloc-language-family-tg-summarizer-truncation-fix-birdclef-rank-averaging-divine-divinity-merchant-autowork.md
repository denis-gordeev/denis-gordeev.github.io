---
title: "AUTOWORK - WoW: Eredun/Pandaren/Vulpera languages, murloc language family; tg_summarizer: truncation fix; BirdCLEF: rank-averaging ensemble; Divine Divinity: merchant trading"
date: 2026-06-10
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository adds three new standard language entries (Eredun, Pandaren, Vulpera), expands the murloc/jinyu/ankoan/kobyss evolutionary language family analysis, and documents kobyss research with Drust Stele catalog and Hallowfall place names. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** fixes a critical summary truncation bug and an indentation issue dropping NLP messages. **[birdclef_2026](https://github.com/denis-gordeev/birdclef_2026)** experiments 048–050 find rank-averaging as the best ensemble so far (+0.087 AUC). **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies English comments, JSDoc, and test descriptions across all target packages. The local **open-divine-divinity-rust-bevy** project adds merchant trading, skill particle effects, and enemy patrol/ranged AI.

## wow_constructed_languages: three new languages, murloc family, kobyss research

Three commits add 1,596 lines of linguistic analysis across 23 files.

### Eredun, Pandaren, and Vulpera standard files (June 9)

Eredun, Pandaren, and Vulpera previously had only index.html pages; now each has the full set of vocabulary.md, grammar.md, description.md, and vocabulary.html — consistent with all other language directories. Cross-references are updated in eredun-draenei-comparative.html, README.md, and titan-forged-comparative.html.

### Kobyss research, Drust Stele catalog, Hallowfall place names (June 9)

- **Kobyss**: 25+ NPC names documented (all Common/English descriptors), ankoan descent lore, tribal designations, and Hallowfall territory places; no kobyss-language data exists
- **Drust Steles**: expanded from 4 to all 10 stele names, added Constructs inscription text, confirmed all steles are pictographic Common descriptions — not Drust-language text
- **Common/Hallowfall**: 9 Arathi personal names, 12+ place names, possessive naming pattern analysis, Danath Trollbane update
- **Ethereal**: Devouring Host faction, Dark Heart artifact, Voidstorm concept; updated Locus-Walker and Soul-Scribe entries; expanded Ravel notes

### Murloc/jinyu/ankoan/kobyss language family analysis (June 9)

Full evolutionary chain documented from Murloc (Nerglish) through Jinyu and Ankoan to Kobyss, based on warcraft.wiki.gg data. Key findings: 5 ankoan names, 30+ jinyu names, Nerglish phonotactic patterns, and kobyss linguistic regression (only 3–5 Common words attested). Expanded kobyss section with 7 tribes, 5 chieftain names, and a cross-family phonological comparison table.

## tg_summarizer: critical truncation fix and cost optimization

A critical bug is fixed: `UPDATE_SUMMARY_MAX_TOKENS` was set to 500 but the prompt asks for a full summary, causing silent data loss via truncation. Now set to 2000 tokens. An indentation bug caused `nlp_related_messages.append` to execute outside the for loop, dropping all but the last message per batch. Additional improvements: intra-batch dedup is now run before coverage checks (saves LLM tokens on duplicates); coverage context is built once per call instead of per-message; `ENABLE_SUMMARIES_DEDUPLICATION` and `ENABLE_SUMMARY_UPDATES` are now env-configurable; `extract_links` strips trailing punctuation from URLs; length guard in `update_existing_summary` falls back to append on truncation. **14 new tests bring the total to 146, all passing.**

## birdclef_2026: experiments 048–050

Three new experiments in the BirdCLEF 2026 competition pipeline, adding 2,857 lines across notebooks and scripts.

### 048 Extended soundscape training (MIXED) (June 9)

Extended experiment 047 with MLP probes, cosine prototypes, probe ensembling, shrunk alpha tuning, and pseudo-labeling. **MLP overfits** (9/67 species better than LR, delta -0.065). **Cosine prototypes fail** in PCA space (AUC 0.56). Probe ensembling is marginal (+0.037 vs +0.036). Pseudo-labeling adds nothing. **Tax blend remains best at +0.073 AUC.**

### 049 Rank-averaging ensemble (POSITIVE) (June 9)

**Rank-averaging ensemble achieves +0.087 AUC**, beating the previous best tax_blend (+0.073) by +0.014. This is the strongest result so far.

### 050 Meta-augmented probes (NEGATIVE) (June 9)

Augmenting probes with baseline/site/hour features hurts performance due to focal-soundscape distribution mismatch. The rank-averaging ensemble from 049 remains the best approach.

## ru-skill: russification of comments and JSDoc

English comments, JSDoc, and test descriptions are russified across all target packages (yandex-rasp, osm-nearby, zoon-nearby, kinopoisk-search, stoloto-lotto, rpl-results, pravo-documents, kakao-bar-nearby, airkorea, mchs-storm-warnings). Doc-regression expanded to cover mchs-storm-warnings. **131 tests pass, 1 skipped.**

## open-divine-divinity-rust-bevy: merchant trading, particle effects, enemy AI

A significant feature update adds **merchant trading** (buy/sell items with gold), **skill particle effects**, and **enemy patrol/ranged AI** (Orc Archer as a new ranged enemy type). Over 1,000 lines added across game.rs and game/combat.rs.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
