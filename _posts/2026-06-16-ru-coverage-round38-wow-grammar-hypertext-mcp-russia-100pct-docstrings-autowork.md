---
title: "AUTOWORK - My-RU-Coverage: round #38 russification; WoW: grammar & description hypertext for 29 languages; MCP-Russia: 100% docstring coverage"
date: 2026-06-16
layout: post
---

The **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** repository reaches round #38, replacing 12+ anglicisms with native Russian equivalents across financial and business terminology. **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** adds grammar.html and description.html hypertext pages for all 29 documented languages. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** achieves 100% docstring coverage with Russian documentation for all functions, plus ЕМИСС code verification.

## My-RU-Coverage: round #38 — business & financial russification

One commit modifies 28 files.

### Terminology replacements

Round #38 targets financial and corporate anglicisms:

| Anglicism | Russian replacement |
|-----------|-------------------|
| бренд | торговая марка |
| дискаунтер | магазин низких цен |
| лизинг | аренда |
| маркетинг | сбыт/продвижение |
| банкинг | банковское дело |
| вендор | поставщик |
| бизнес-процессы | деловые процессы |
| колокация | совместное размещение |
| хостинг | размещение на сервере |
| секьюритизация / клиринг | пояснения |
| рекламный инвентарь | рекламные площади |
| офлайн-сеть | сеть физических отделений |
| РФ-сегмент | российский сегмент |

МСФО and РСБУ abbreviations are expanded with explanations. An erroneous alias mapping EV→электромобиль is removed.

## wow_constructed_languages: grammar & description hypertext for 29 languages

One commit adds grammar.html and description.html (hypertext) pages for all 29 documented constructed languages. This provides browsable, cross-linked grammar references and language descriptions alongside the existing vocabulary HTML pages, completing the hypertext documentation suite.

## mcp-russia: 100% Russian docstring coverage

Two commits bring complete Russian-language documentation to all functions in `data/client.py`.

### 110 undocumented functions → Russian docstrings

A first pass adds Russian docstrings to 110 previously undocumented functions across 11 modules in `data/client.py`.

### Final 11 functions — 100% coverage

A second pass documents the last 11 functions and verifies all ЕМИСС (Unified Interdepartmental Statistical Information System) codes, reaching full docstring coverage across the entire codebase.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
