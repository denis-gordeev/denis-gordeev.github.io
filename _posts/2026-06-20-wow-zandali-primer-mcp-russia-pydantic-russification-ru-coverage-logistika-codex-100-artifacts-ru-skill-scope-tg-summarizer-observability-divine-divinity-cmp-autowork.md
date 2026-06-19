---
title: "AUTOWORK - WoW: Zandali primer with confirmed sentences and verb morphology; MCP-Russia: Pydantic schemas + 1915 constants russified; My-RU-Coverage: round #43 + логистика elimination; Codex: 100 translation artifacts; Ru-Skill: scope/server terms russified; TG-Summarizer: circuit breaker observability; Divine Divinity: CMP archive parser"
date: 2026-06-20
layout: post
---

Seven repositories see updates in this round. **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** publishes the first confirmed Zandali sentences and verb morphology from the patch 12.1.0 primer. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies ~2000 code-level identifiers across 93 files. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** reaches round #43 and eliminates «логистика». **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** fixes ~100 more translation artifacts. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies scope, server, and legacy terms. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds circuit breaker observability. **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds real game asset loading with CMP archive parser.

## wow_constructed_languages: Zandali primer and verb morphology

Three commits (1374 insertions, 20 files) deliver the most significant Zandali update yet.

### Patch 12.1.0 Curse of Ula'tek and confirmed primer words

- **Ula'tek** (snake goddess) added with official IPA /ˈuːlə.ˌtɛk/ — first WoW conlang word with confirmed IPA
- **30+ confirmed Zandali words** from Moldy Diary and Hastily-Scribbled Note: verbs (File/Fele love, Kele/Kile rise, Peran/Poran die), grammatical words (De, Den, Ko, Na, Nekan)
- **3 confirmed native Zandali sentences** with translations — the first ever: Tokobo'ne na Amani'Zar, Doba quzhu ta tawbo, Untoh de alanke tono
- Verb morphology: singular/plural ablaut, person suffixes (-den/-ne/-nekan)
- Akil'='Eagle' prefix (2 attestations), confirmed Basengo='Slashed tree', Shan'aten='Ashen pine'
- 8 new NPCs, expanded pronoun system with Ko, Moi, Midi, Nekan, Den from confirmed primer

### Deepened Zandali analysis

- Verb morphology: ablaut patterns, suffix paradigms, syntactic patterns
- Kith'ix Aqir transmission hypothesis
- Writing system analysis
- 60+ wiki proper nouns integrated
- Speculative morphemes catalogued

### MD/HTML sync fixes

Heading name mismatches fixed in nature/pandaren/vulpera, haranir grammar bold and missing item restored.

## mcp-russia: Pydantic schemas and 1915 constants russified

One commit (13417 insertions, 93 files) completes the deepest code-level russification pass yet:

- **~67 Pydantic schema field replacements** across all 22 modules
- **~1915 constants.py key replacements** — Russian identifiers replace English keys throughout data dictionaries
- **~60+ function parameter replacements** — client tools and function signatures now use Russian parameter names
- Full coordination across schemas/constants/client/tools/tests in all modules

This brings the codebase to near-complete Russian identifier parity from schemas to API tool descriptions.

## My-RU-Coverage: round #43 and «логистика» elimination

Two commits (447 insertions, 80 files).

### Round #43

- дата-центр → центр обработки данных (ЦОД), инжиниринг → инженерно-технический
- трейдеры → торговые компании/участники торгов, дистрибьюторы → оптовые поставщики
- маркетмейкеры → поставщики ликвидности, дженерики → препараты-аналоги
- софт → программное обеспечение, биллинг → расчётно-учётные системы
- концерн → холдинг, продуктовый микс → ассортимент, экспозиция → доля
- Abbreviations expanded: ТНП, ИБП, НПЗ, АЗС, ЖБИ, ГОК, САПР, СУБД
- WIKILINK_ALIASES +20 new aliases

### «Логистика» elimination

- логистика → транспортно-складское обеспечение (48 occurrences, 20 reports)
- логистический оператор → оператор перевозок и хранения
- логистическая инфраструктура → инфраструктура перевозок и хранения
- All 42/42 reports pass audit

## codex-console-english: 100 more translation artifacts

Two commits (279 insertions, 38 files):

- **~100 Chinese calques eliminated**: modal box→modal, fill in→enter, heartbeat detection→check, configuration→settings, exit IP→outgoing IP
- **Last Chinese characters removed**: 对应的 replaced with English description in README.md and TODO.md
- 36 files touched across Python services, JavaScript, and HTML templates

## ru-skill: scope and server terms russified

One commit (236 insertions, 21 files):

| Anglicism | Russian replacement |
|-----------|-------------------|
| scope | область действия |
| Endpoint | Эндпоинт |
| server-to-server | межсерверной |
| server-side | серверно отрендеренный |
| API proxy | прокси |
| booking-навыков | навыков бронирования |
| Legacy-совместимый | обратно совместимый |
| Legacy-резерв/файл/имя/формулировка | устаревш* |
| Local Telegram mirror | Локальный зеркальный канал |

Doc-regression tests expanded by 131 lines.

## tg_summarizer: circuit breaker observability

One commit (153 insertions, 7 files):

- **Circuit breaker state in Lambda response**: callers can now see breaker status (closed/open/half-open) in every summarization response
- **Prompt anti-verbosity**: system prompt tuned to suppress unnecessary hedging
- **Temperature sync fix**: environment variable and SAM template now stay consistent
- **gpt-4.1-mini cost table**: token pricing for the newer model added to cost tracking
- 110 new tests

## open-divine-divinity-rust-bevy: real game asset loading

One commit (1060 insertions, 8 files) implements the first phase of loading assets from actual Divine Divinity installations:

- **CMP Family A archive parser** with 32-byte XOR key name deobfuscation (sound.cmp, global.cmp, flat.cmp, text.cmp, mono.cmp)
- **CPacked sprite index reader**: enumerates entries from CPackedi.\* files with width, height, flags, and hotspot metadata
- **DDS texture format** support via image crate's dds feature
- **3-tier sound loading**: loose files → CMP archives → procedural fallback
- Asset debug panel shows CMP archive and CPacked sprite pack info
- 17 new tests (591 → 608 total)

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
