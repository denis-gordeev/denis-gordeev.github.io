---
title: "AUTOWORK - WoW: IPA phonology charts for 11 languages, dialectal variation for 17; Ru-Skill: 17-term russification; TG-Summarizer: Lambda hardening round 26; My-RU-Coverage: round #41; Codex: translation polish"
date: 2026-06-18
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository receives its largest structural update yet: IPA phonology charts for 11 languages, attestation tables for 6, and dialectal variation sections for 17. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies 17 more terms and expands doc-regression tests. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** ships Lambda hardening round 26 with 11 new tests. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** reaches round #41. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** polishes remaining translation artifacts.

## wow_constructed_languages: IPA phonology, attestation, dialectal variation

Three commits (18559 insertions, 121 files) represent a comprehensive structural upgrade across the entire language collection (now 30+ languages).

### IPA phonology charts (11 languages)

Proper IPA consonant and vowel charts added to:

- **Darnassian, Orcish**: full phonology sections in grammar pages plus expanded descriptions
- **Zandali, Thalassian**: phonology added to grammar; descriptions expanded with Nazja cross-references
- **Dwarven, Earthen, Draenei, Mogu, Nerubian, Qiraji, Sethrak, Shath'Yar, Titan**: IPA tables standardized in both Markdown and HTML

Each chart follows a consistent template: consonant inventory (place × manner), vowel quadrilateral, and phonotactic constraints.

### Attestation tables (6 languages)

Structured attestation summary tables added to Draenei, Dwarven, Earthen, Eredun, Mogu, and Pandaren descriptions — cataloguing every confirmed in-game word or name with source expansion (Classic through The War Within / Midnight).

### Dialectal variation sections (17 languages)

New dialectal variation subsections added across 17 language descriptions, covering:

- **Darnassian**: Highborne vs. modern night elf registers
- **Orcish**: Blackrock vs. Frostwolf dialectal differences
- **Dwarven**: Bronzebeard / Wildhammer / Dark Iron; Earthen of Khaz Algar as distinct dialect; Skardyn divergence
- **Draenei**: Eredun-influenced loan phonology vs. standard Draenei
- **Nerubian**: Azjol-Nerub vs. Nerub'ar vocabulary
- **Qiraji**: Silithid caste register differences
- **Vrykul**: regional clan name variation
- Plus Gutterspeak, Kalimag, Mogu, Nature, Nerglish, Pandaren, Sethrak, Shath'Yar, Tolvir, Vulpera

All HTML counterparts synced.

### Morphological analyses

New morphological analyses added for Darnassian and Orcish grammar pages, including attested morpheme breakdowns and comparative notes.

## ru-skill: 17-term russification + doc-regression expansion

One commit (269 insertions, 24 files) replaces 17 anglicisms with Russian equivalents:

| Anglicism | Russian replacement |
|-----------|-------------------|
| side effects | действия с побочными эффектами |
| holdings | позиций |
| pixel-perfect | точную |
| watchlist | список наблюдения |
| waitlist | лист ожидания |
| scope | область действия |
| inline- | встроенные |
| canonical | канонический |
| merchant-level | со стороны продавца |
| anchor-точка | опорная точка |
| slug | идентификатор |
| ingress | входной прокси |
| extraction | извлечение |
| flow | потоки |
| dry-run | пробный запуск |
| фикстура | эталонные данные |
| слаг | идентификатор |

Doc-regression tests expanded by 189 lines to cover all new replacements.

## tg_summarizer: Lambda hardening round 26

One commit (340 insertions, 10 files) with 5 improvements and 11 new tests (255 total):

- **HTML entity counting**: `html.unescape()` after tag stripping so `&amp;`/`&lt;`/`&gt;` count as 1 character
- **fsync durability**: `save_json_file` calls fsync before atomic replace on Lambda
- **Cost guard**: warn when `OPENAI_MODEL` not in cost table (gpt-4o-mini pricing guard)
- **Hash dedup**: `_remove_intra_batch_duplicates` uses text_hash pre-filter for O(1) exact dedup
- **S3 empty-file guard**: skip 0-byte uploads to prevent S3 state overwrite

## My-RU-Coverage: round #41 — SaaS/IaaS russification

One commit (140 insertions, 13 files) removes English echo brackets around leasing/hosting/colocation/Tier/IaaS/SaaS/BaaS/DRaaS/SLA, adds Russian canonical forms to `APPLICATION_TERMS`, and adds new aliases for SaaS, IaaS, SLA. Discovery pipeline updated with ИИ and интернет вещей.

## codex-console-english: OTP and health status polish

One commit (71 insertions, 17 files) polishes remaining translation artifacts: OTP terminology consistency, `whether` → natural English, email data fields, and health status phrasing across services, routes, templates, and JavaScript.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
