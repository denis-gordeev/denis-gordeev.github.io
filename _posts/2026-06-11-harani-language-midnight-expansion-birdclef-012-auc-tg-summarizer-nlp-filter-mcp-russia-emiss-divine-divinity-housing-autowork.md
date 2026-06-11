---
title: "AUTOWORK - WoW: Hara'ni language, Midnight expansion data; BirdCLEF: +0.1207 AUC 3-way rank-averaging; tg_summarizer: NLP pre-filter; MCP-Russia: ЕМИСС; Divine Divinity: housing & companions; My-RU-Coverage & ru-skill russification"
date: 2026-06-11
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository adds the Hara'ni (Haranir) language section with full linguistic analysis, expands with Wikipedia-confirmed TWW/Midnight data, and deepens Haranir morphology. **[birdclef_2026](https://github.com/denis-gordeev/birdclef_2026)** reaches a new best of +0.1207 AUC with 3-way rank-averaging. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds NLP keyword pre-filtering (30-50% call savings), combined coverage+match checks, and cost optimizations. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** gains a universal ЕМИСС indicator tool and Rosstat regional comparisons. **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds player housing, companion system, puzzle dungeons, and enchanting. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** eliminates the "Не определено" sector and fixes 37 grammar errors. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies remaining English jargon and JSDoc.

## wow_constructed_languages: Hara'ni language, Midnight expansion, TWW updates

Four commits add 19,594 lines across 21 files — the largest update since the initial nerubian analysis.

### Hara'ni (Haranir) language section

A new `haranir/` directory provides vocabulary.md, grammar.md, description.md, and vocabulary.html. Key findings: 12+ NPC names, 3 place names, 5 cultural names, and the language name Hara'ni confirmed from the wiki infobox. Morphological analysis identifies the Hara- root (5 attestations), proposed -nir/-ni/-ti suffix set, and a -dar toponymic suffix likely borrowed from Earthen/Arathi. No confirmed genetic relationship to elven, troll, titan-forged, or Aqir-descended families. All 10 Drust Stele inscription texts recovered from warcraft.wiki.gg; key finding: Flayed Man stele references illegible runic prayers; Breath Into Stone stele describes spirit-transfer ritual into stone. Corrected error: no stele titled 'The Three' (was confusion with 'The Tree').

### Haranir linguistic deepening

The -ia feminine suffix is identified across Haranir names. Haranir-nerubian loanwords are documented. A Greenspeaker/Thornspeaker parallel is drawn with Haranir nature terminology.

### Wikipedia-confirmed TWW data

Haranir files updated with Undermine patch (Lingering Shadows) details: Orweyna's story, additional unnamed Haranir NPCs, Worldsoul vision, isolationist tension, and Opportunity Point scouting. Ethereal vocabulary expanded with Ghosts of K'aresh campaign: Shadowguard/Wastelander oath dynamics, Ravel-Xal'atath connection, Dark Heart journey. Legacy of Arathor factions added to Common vocabulary (Red Dawn, Scarlet Crusade, Syndicate, Defias Brotherhood). Gnomish vocabulary updated with Gallywix/Nikki fates, Renzik martyrdom, Siren Isle.

### Midnight expansion language data

Aln- root confirmed across Darnassian and related languages. Ruutani and Hash'ey names documented. The domanaar construction analyzed. Zandali -ey suffix (diminutive/honorific) identified with 12 grammar rules and 18 vocabulary entries.

## birdclef_2026: new best at +0.1207 AUC

Three new experiments add 3,469 lines.

### 051 Per-taxon rank-averaging (+0.1024 AUC, near-oracle)

Per-taxon rank-averaging reaches +0.1024 AUC, approaching oracle performance. Site embeddings (experiment 012) are confirmed negative — they don't help the pipeline.

### 052c 3-way rank-averaging (+0.1207 AUC) — new best

Adding Perch raw scores as a third signal source in rank-averaging beats 051 by +0.0182 AUC. Base weight drops to 0 — LR+Perch are sufficient. Oracle gap: only 0.0017. **This is the strongest result so far, +0.034 above the previous best from the last round.**

### 052 and 054: probe techniques (negative)

Embedding smoothing, context features, oversampling, and weighted focal loss are all neutral/negative in experiment 052. Multi-view probes (054) show that same-embedding PCA dims provide redundant signal in rank-averaging. 708 labeled windows remains the fundamental bottleneck.

## tg_summarizer: NLP pre-filter, combined checks, cost optimization

Two commits add 25 new tests (total 171, all passing) with significant cost and reliability improvements.

### NLP keyword pre-filter (30-50% call savings)

Obvious ads/courses/webinars are filtered before LLM invocation, saving approximately 30-50% of NLP calls.

### Combined coverage+match check

Two separate LLM calls (_check_coverage + find_relevant_summary) merged into a single call, saving one call per covered message.

### Config validation and error handling

All integer configs use _get_int_env (rejects zero/negative). validate_config() moved inside try/except in lambda_handler with structured error returns. should_run_group_summarization returns True on parse errors (was False, blocking forever). process_covered_message refreshes matching_summary from file to prevent stale updates.

### Cost optimization

OPENAI_CHANNEL_SUMMARY_MAX_TOKENS reduced from 4000 to 1500 (sufficient for 4000-char summaries). Input truncation added in _check_coverage_and_match and update_existing_summary. Dead code removed: is_message_covered_in_summaries/is_message_covered_in_group_summaries and DUPLICATE_CHECK_PROMPT.

### Lambda hardening

Deadline propagation into process_messages with checks before NLP/coverage/summary phases. Cached _load_processed_messages results. Total examined message limit (MAX_MESSAGES_PER_SOURCE*3) in _fetch_from_sources.

## mcp-russia: ЕМИСС universal tool, Rosstat expansion

Two commits add 765 insertions across 19 files.

### Универсальный инструмент indikator_dannye (ЕМИСС)

A new universal tool wraps the ЕМИСС (Unified Interagency Information and Statistical System) API, providing access to any Russian federal statistical indicator. format_rub is fixed, API tokens unified, and duplicate subject entries eliminated.

### Расширение Росстата

Rosstat tools now support GRP (ВРП), salary data, and regional comparisons. Portuguese test fixtures cleaned up. 97 new test lines added for Rosstat tools.

## open-divine-divinity-rust-bevy: housing, companions, enchanting

Two commits add 4,068 lines across 8 files — a major feature update.

### Player housing, merchant restocking, skill tree

Player housing system allows owning and furnishing a home. Merchants now restock inventories. A skill tree provides structured character progression. Friendly NPC crossfire: allied NPCs engage enemies in combat.

### Companion system, puzzle dungeons, enchanting

A full companion system with AI followers. Puzzle dungeons with environmental puzzles and traps. An enchanting system for item enhancement. Minimap markers for points of interest.

## My-RU-Coverage: sector cleanup, grammar fixes

Two commits modify 80 files (988 insertions, 553 deletions).

### Eliminated "Не определено" sector

ASTR remapped to Технологии, CNRU to Недвижимость — the undefined sector is gone. 37 grammar errors fixed across 18 reports (case disagreements, incorrect forms after prepositions, list and wiki-link errors).

### Mass wiki-link conversion

318+ generic wiki-links converted to plain text across 42 reports. Russian explanations added for процессинг/маркетмейкер/листинг. SECTOR_THEME_MAP introduced for automatic theme generation. min_weight raised from 2 to 5 in build_network.py for cleaner graph edges.

## ru-skill: final English jargon russification

Remaining English jargon russified: lookup, real-time, nearby, Sold out, Write-, aggressive polling, HTML scraping. JSDoc and source code comments translated. doc-regression test suite expanded.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
