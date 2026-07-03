---
title: "AUTOWORK - WoW Rounds 20-22, Divine Divinity pathfinding, MCP-Russia test russification, RU-Coverage round 58, ru-skill round 74, Codex-Console round 61"
date: 2026-07-04
layout: post
---

Six repositories see new commits since July 3: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships three rounds (20-22) with Shath'Yar massive expansion, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds A* pathfinding and global ID validation, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies test fixtures across all data modules, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships round #58, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 74 with package READMEs, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** confirms round 61.

## wow_constructed_languages: Rounds 20-22 — Shath'Yar expansion to 63+ phrases, Darnassian conditioning, Zandali phonology

Three commits (Rounds 20, 21, 22):

### Round 20 — Alien comparative expansion, Shath'Yar locative fronting

- **Nerglish jinyu analysis**: phonological trajectory table, key parallels, -shi suffix analysis, linguistic expansion/loss patterns
- **Kalimag & Taur-ahe parallels**: both support Blizzard design convention hypothesis over in-universe transmission
- **Hara'ni -dar suffix**: Harandar is first non-titan-forged language with borrowed -dar toponymic suffix
- **Zandali -mara = balance**: two attestations (Shaol'mara, Kul'amara) provide circumstantial support; confidence Very Low → Low-Moderate
- **Nazja -ah reflex**: Nazj-/Nazja pair identified (Low-Moderate confidence); updates Darnassian Investigation 14 and elven-comparative Correspondence 7
- **Shath'Yar**: code 3 phrases including locative fronting pattern (Skitsh qi'uthik illith!); total 40+ → 43+

### Round 21 — Three-way negation, Darnassian phonological conditioning, Zandali Bwon'

- **Shath'Yar**: code 12 new phrases (55+ total); add three-way negation system; massive grammar expansion (+168 lines in grammar.md)
- **Darnassian**: add phonological conditioning investigation with -na/-la/-ra alternation analysis
- **Zandali**: add Bwon' death prefix, -mara morpheme testing
- **Elven comparative**: update with new Darnassian evidence

### Round 22 — Zandali Investigation 6B, phonological patterns 13-16, Shath'Yar 63+, Satyrnaar counterexample

- **Zandali Investigation 6B**: *no* connective in loa names — four hypotheses (genitive, vocative, possessive, cognate with Thalassian); dedicatory/cognate interpretation preferred at Low-Moderate confidence
- **Akunda** as potential -da evidence beyond kinship (Very Low-Low confidence)
- **Phonological patterns 13-16**: CV'CV naming template for Amani NPCs, blood troll phonological divergence, -ara/ari/aru vowel alternation family, /a/-dominance hierarchy by morpheme type
- **Shath'Yar**: code 8 additional confirmed phrases (63+ total); potential new negation elements (*sythn*, *nuq*, *Naza*)
- **Darnassian Investigation 8**: *Satyrnaar* identified as counterexample to phonological conditioning hypothesis; Common-borrowing explanation proposed; conditioning exceptionless across 12 native attestations

---

## open-divine-divinity-rust-bevy: Global ID validation, sprite categorization, A* pathfinding

One commit (377 insertions, 26 deletions, 5 files):

- **resolve_global_id()** and **validate_global_id_overlay_mappings()** in CpackedCollection for dimension-based validation of overlay ID mappings
- **Sprite categorization**: ObjectCatalog classifies doors/chests/levers → objects, walk-on → tiles, large sprites → enemies/NPCs with dimension-based fallback
- **Walkability**: WorldCell.is_walkable() in from_world_partition(); blocking object detection (locked doors/chests mark tiles as Wall)
- **A* pathfinding**: find_path_astar for maps >200 tiles, BFS for smaller maps
- 4 new tests (781 → 785 total)

---

## mcp-russia: Test fixture russification across all data modules

One commit (529 insertions, 479 deletions, 30 files):

- Russify test suffixes, _mock_ctx fixtures, and string values across all 20 data module test files
- Shared test infrastructure: test_batch.py, test_cache.py, test_feature.py, test_formatting.py
- Data modules: cbrf, cekrf, fns, fssp, gibdd, gosduma, kad_arbitrazh, kaznacheistvo, mchs, minobrnauki, minzdrav, publikatsii, rosapi, rosaudit, rosgidromet, roskomnadzor, rospotrebnadzor, rosprirodnadzor, rosstat, rosvodresursy, sovfed, zakupki

---

## My-RU-Coverage: Round #58

One commit:

| Category | Change |
|----------|--------|
| Latin wikilinks → Cyrillic | [[Ozon Банк]]→[[Озон Банк]], [[OZON]]→[[Озон]], [[Kaspersky]]→[[Касперский]], [[Wildberries]]→[[Вайлдберриз]] |
| English display text | Astra Desktop Management → Russian equivalent |
| партнёр replacements | → контрагет/совместный/сотрудничество (20 occurrences, 13 reports) |
| Dictionaries updated | WIKILINK_ALIASES, LOCAL_COMPANY_TICKERS, TECH_TERMS, APPLICATION_TERMS |
| Enrichment JSON | TATN, NVTK refreshed |

---

## ru-skill: Round 74 — Package READMEs and roadmap

One commit (84 insertions, 26 deletions, 8 files):

- Update package READMEs: k-skill-proxy, kleague-results, rpl-results, zoon-nearby
- Expand roadmap documentation in docs/roadmap.md
- Strengthen skill-docs.test.js regression tests (+56 lines)

---

## codex-console-english: Round 61

One commit (7 insertions, 1 file):

- Verified fully English; all tests pass; no non-English text found

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
