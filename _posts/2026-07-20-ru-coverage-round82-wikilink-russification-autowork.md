---
title: "AUTOWORK - RU-Coverage round 82: Latin wikilinks→Russian aliases, args→аргументы, parser→парсер, f→ф"
date: 2026-07-20
layout: post
---

One monitored repo lands a meaningful update on July 20. **My-RU-Coverage** completes russification round 82, replacing Latin identifiers in scripts and wikilinks across 23 files with Russian equivalents. The remaining 7 repos show no new feature commits.

## My-RU-Coverage: Round 82 — Script variable and wikilink russification (284 insertions, 23 files)

### Latin variable names → Russian

Six scripts replace `args` with `аргументы`: `add_ticker.py`, `build_themes.py`, `discover.py`, `update_enrichment.py`, `update_financials.py`, `update_valuation.py`. The `f` file-handle variable becomes `ф` in `build_network.py`, `build_themes.py`, `build_wikilink_index.py`. The `discover.py` loop variable `f` becomes `файл`, `m` (regex match) becomes `совпадение`, `fh` becomes `дескриптор`. In `utils.py`, `parser` → `парсер` inside `создать_русский_парсер()`. In `update_enrichment.py`, the list comprehension variable `a` becomes `элемент`.

### Wikilink index cleanup

12 Latin wikilinks are replaced with Russian aliases: Самолёт (from Самолет), НОВАТЭК, ДОМ.РФ normalized to proper capitalization. Generic wikilinks for КОМ and РСВ removed. The index shrinks from 311 to 306 unique wikilinks. Foreign companies section drops from 7 to 3 entries (Huawei, Ericsson, Dell, Cisco removed). Russian companies section grows from 88 to 93 as reclassified entries move.

### Pilot report normalization

8 pilot report files updated with normalized company name casing: ЭЛ5-Энерго, Циан, МТС, БАЗИС, Системата, РОСНАНО, Сбер, ВТБ.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
