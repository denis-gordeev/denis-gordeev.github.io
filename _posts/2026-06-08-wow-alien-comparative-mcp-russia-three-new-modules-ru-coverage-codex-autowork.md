---
title: "AUTOWORK - WoW: alien-languages comparative page, attested nerubian scrolls, 15+ ethereal names; mcp-russia: three new Russian modules; My-RU-Coverage: abbreviation russification"
date: 2026-06-08
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository continues its deep linguistic analysis with a new alien-languages comparative page, attested nerubian scroll text, Ky'veza reclassification, and 15+ new ethereal names. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** disables all 27 legacy Brazilian modules and adds three new Russian government modules — Совет Федерации, Федеральное казначейство, and Росприроднадзор. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** continues russification with abbreviation expansion and Russian CLI placeholders. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** cleans up non-ASCII formatting characters.

## wow_constructed_languages: alien comparative page, attested texts, expanded vocabularies

Three commits bring significant new linguistic analysis and cross-language comparison.

### Reshii/-esh analysis and apostrophe cross-reference (June 8)

The **Reshii** element in ethereal vocabulary is connected to the **K'aresh -esh/-resh** root form, upgrading the **-esh** locative suffix confidence to Moderate. A cross-reference of alien apostrophe naming conventions across Shath'Yar, nerubian, qiraji, and ethereal identifies two distinct apostrophe patterns: **initial-prefix** vs **medial-compound**, proposing an Old God → Aqir transmission chain. The **Gallagio -gio/-agio** morpheme is investigated and concluded to be an Italian aesthetic choice by Blizzard (High confidence), not a genuine goblin morpheme. Legacy of Arathor names (Marran Trollbane, Veronica Nials, Stromgarde) are added to the common vocabulary with no new Vrykul morpheme evidence. The **-naxx/-nax** pattern analysis is deepened with x=/ks/ vs /x/ ambiguity, explaining -naxx as /næxː/ to avoid /næksks/ phonological difficulty.

### Alien-languages comparative page (June 8)

A new **alien-comparative.html** page is added, providing a side-by-side comparison of Shath'Yar, nerubian, qiraji, and ethereal languages — enabling systematic cross-language morphological and phonological analysis.

### Major wiki verification: attested texts and expanded vocabularies (June 8)

The largest commit in this round brings attested nerubian scroll text, the **Azj'Aqir** name, 15+ new ethereal names, **Ky'veza** reclassification, and expanded earthen and nerubian vocabularies. This represents a major verification pass against official wiki sources.

## mcp-russia: three new Russian modules, Brazilian modules disabled

The project pivots fully toward Russian government data by disabling all 27 legacy Brazilian modules (`enabled=False`) so their Portuguese-named tools no longer load. Three new Russian modules are added:

- **Совет Федерации** (sovfed): Federation Council data from council.gov.ru
- **Федеральное казначейство** (kaznacheistvo): Federal Treasury from roskazna.ru
- **Росприроднадзор** (rosprirodnadzor): Environmental oversight from rpn.gov.ru

Tests and docs are updated to reference active Russian modules. The module count grows from 19 to **22 active Russian modules**.

## My-RU-Coverage: abbreviation russification

Russian abbreviation expansion continues with ДПМ/ДБО/РКО/NPK/MOEXBC/ПВЗ/ОРЭМ, Russian CLI placeholders, and multiplier footnotes (P/E/P/S/P/B/EV/EBITDA). Nine pilot reports are updated (OZON, ЭЛ5-Энерго, Акрон, Х5, Аэрофлот, МТС, Банк Санкт-Петербург, МКБ, Сургутнефтегаз), along with graph data and enrichment scripts.

## codex-console-english: non-ASCII cleanup

Two commits clean up formatting: non-ASCII formatting characters are replaced with ASCII/HTML-entity equivalents (Round 27), and a TODO update confirms all 29 tests pass with no remaining non-English text (Round 28).

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
