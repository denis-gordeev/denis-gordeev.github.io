---
title: "AUTOWORK - WoW: massive vocabulary HTML rebuild for 18 languages; MCP-Russia: documentation russification; Codex: 233 translation artifacts; Ru-Skill: legacy compounds russified; TG-Summarizer: circuit breaker; Divine Divinity: combo visual feedback; My-RU-Coverage: round #42"
date: 2026-06-19
layout: post
---

Seven repositories see updates in this round. **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships a massive MD/HTML vocabulary sync across 18 languages. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies documentation headers and terminology across 16 files. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** fixes ~233 translation artifacts. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies legacy compound terms. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds configurable circuit breaker with half-open recovery. **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds combo visual feedback. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** reaches round #42.

## wow_constructed_languages: massive MD/HTML vocabulary sync

One commit (5148 insertions, 36 files) rebuilds 18 vocabulary.html files, fixes Darnassian description.html missing sections, integrates Additional Canon Phrases into grammar for 3 languages, adds Thalassian Midnight content, fixes attestation summaries, and validates all 30 language directories.

### Vocabulary HTML rebuilds (18 languages)

Full HTML regeneration for Drust (+641), Ethereal (+791), Harani (+873), Nerubian (+866), Tolvir (+995), and significant updates for Draenei, Dwarven, Earthen, Gnomish, Gutterspeak, Mogu, Nazja, Qiraji, Shath'Yar, Shalassian, Taur-ahe, Titan, Vrykul, and Zandali. Each file now reflects the latest Markdown source with consistent formatting and cross-references.

### Grammar and description fixes

- **Darnassian**: missing sections restored in description.html; morphological analysis and Additional Canon Phrases integrated into grammar
- **Orcish**: Additional Canon Phrases integrated into grammar
- **Taur-ahe**: grammar.html updated
- **Thalassian**: Midnight content added to description and grammar

## mcp-russia: documentation russification

One commit (199 insertions, 21 files) replaces ~140 English headings and labels with Russian equivalents across 16 documentation files:

- **feature → модуль**, **tools → инструменты**, **Prompt: → Промпт:**
- English section headers in architecture, configuration, development, and all 7 example prompts replaced with Russian
- Contributing guide and quickstart fully russified

## codex-console-english: 233 translation artifacts fixed

One commit (281 insertions, 33 files) eliminates ~233 residual translation artifacts:

- **has been → active voice**: passive constructions rewritten throughout services and routes
- **Noun+failed → Failed to verb**: error messages normalized to English conventions
- **Chinese-style patterns**: remaining Chinese character artifacts replaced with English equivalents in JavaScript and Python

## ru-skill: legacy compound russification

One commit (193 insertions, 19 files) russifies compound terms:

| Anglicism | Russian replacement |
|-----------|-------------------|
| legacy- compounds | устаревш* |
| adapter'ы | адаптеры |
| job-search | поиска работы |
| remaining | оставшиеся |

Doc-regression tests expanded by 124 lines.

## tg_summarizer: configurable circuit breaker

One commit (290 insertions, 9 files) adds production-grade resilience:

- **Circuit breaker configurability**: threshold, timeout, and half-open recovery exposed via environment variables and SAM template
- **Half-open recovery**: gradual traffic restoration after breaker opens
- **Lower summary temperature**: reduced from 0.5 to 0.3 for more concise summaries
- **205 new tests** for circuit breaker configuration

## open-divine-divinity-rust-bevy: combo visual feedback

One commit (236 insertions, 3 files) adds combo system visual feedback:

- HUD combo counter display
- Floating text on combo hits
- Combo hit particle effects
- All wired into the existing combat combo system

## My-RU-Coverage: round #42

One commit (190 insertions, 18 files) continues financial and corporate russification:

- **провайдер → поставщик** (GMKN, NVTK), **девелопер → застройщик** (MAGN)
- **клиринг → взаимозачёт обязательств** (MOEX), **секьюритизация → устранена** (DOMRF)
- Russian canonical names: Yandex Облако, VK Облако, МТС Облако, МТС Премиум, Группа SCM, Селектел
- WIKILINK_ALIASES reverse mapping, $→₽ fallback, LNG removed

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
