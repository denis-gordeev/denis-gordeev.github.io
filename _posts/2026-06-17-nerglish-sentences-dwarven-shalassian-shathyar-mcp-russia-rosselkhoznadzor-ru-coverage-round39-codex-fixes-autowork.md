---
title: "AUTOWORK - WoW: Nerglish example sentences, Dwarven/Shalassian/Shath'Yar description expansions; MCP-Russia: Россельхознадзор module (24th); My-RU-Coverage: round #39; Codex-Console-English: 182 artifact fixes"
date: 2026-06-17
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository adds Nerglish (murloc/jinyu/ankoan/kobyss) constructed example sentences and significantly expands Dwarven, Shalassian, and Shath'Yar language descriptions. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** gains a 24th data module — Россельхознадзор — plus logger/error russification and kad_arbitrazh code transliteration. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** reaches round #39 with industry terminology replacements. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** fixes ~182 translation artifacts.

## wow_constructed_languages: Nerglish sentences & deep description expansions

One commit (459 insertions, 10 files) adds constructed example sentences for Nerglish (murloc, jinyu, ankoan, kobyss) and expands three language descriptions with phonology, morphology, and attestation tables.

### Nerglish example sentences

The Nerglish language family is unique among WoW languages in spanning both linguistic expansion (murloc → jinyu) and linguistic regression (ankoan → kobyss). Constructed sentences cover:

- **Murloc**: gurgling-compound utterances using attested *mrgl-* and *-gurg* morphemes, plus the canonical battle cry
- **Jinyu**: CV/CVC syllable structures using the only confirmed jinyu word *Onoho* ("Deep Shadow") and the *-shi* agentive suffix
- **Ankoan/Kobyss**: deep-sea combat terminology

Nerglish cross-navigation is added across the example-sentences page.

### Dwarven description expansion

The Dwarven description gains sections on phonology, morphology, Titan-Dwarven linguistic connection, and a full attestation summary table:

- **The War Within (2024)** Earthen of Khaz Algar added as a distinct dialect with longer compound names (*Baelgrim*, *Merrix*, *Adelgonn*, *Brinthe*, *Eirich*, *Lufsela*)
- **Titan morphemes preserved in Dwarven**: *Uld-* (city), *Khaz* (forge, 3 attestations including Khaz Algar), *-dun/-den* (fortification), *-modan/-dor* (kingdom)
- **Vrykul cognates**: *-grim* (*Baelgrim* / *Bjarngrim*), *Eir-* (*Eirich* / *Eyir*)
- **Skardyn** of Khaz Algar noted as divergent dialect with possible *Skar-* relation to Vrykul *Skarvald*

### Shalassian description expansion

Shalassian gains phonology, attested morpheme table, and attestation summary:

- **Midnight expansion (2026)**: no new Shalassian-language content yet; domanaar generals use Common/Latin-inspired names
- **Social strata**: Duskwatch, Leyweavers, Withered may represent different linguistic registers
- **7 morphemes analyzed**: *Shal-* (twilight, moderate confidence), *-dorei* (children of, high), *Aran* (sanctuary, moderate), plus 4 low/very-low-confidence elements
- **Elven family link**: cross-reference to elven-comparative.html added

### Shath'Yar description expansion

Shath'Yar gains phonology and morphology sections:

- **Midnight expansion**: *domanaar* — generals of the Devouring Host — added as speakers; Twilight's Blade cultists noted
- **Phonotactic patterns**: C'CVC (*N'Zoth*, *C'Thun*), C'VCVC (*N'raqi*), CCVCC (*Il'gynoth*)
- **6 morphological elements** tabulated: *N'-* (negation/otherness), *-oth* (divine suffix), *-i* (plural), *Il* (heart), *Shath-*, *-Yar*
- **Reduplication**: *ywaq maq ywaq* noted as possible emphasis/plurality marker

## mcp-russia: Россельхознадзор module (24th) & russification

One commit (1184 insertions, 27 files) adds the 24th data module and advances codebase russification.

### Россельхознадзор (Federal Service for Veterinary and Phytosanitary Surveillance)

New module with 9 tools, 3 resources, 2 prompts covering veterinary and phytosanitary supervision data. All tools and docstrings are in Russian, following the ADR-001 architectural pattern (tools delegate HTTP to client.py).

### Russification advances

- **Logger messages**: 19 replacements across server.py, feature.py, http_client.py
- **Error messages**: 9 replacements (ValueError, TypeError, HttpClientError)
- **Docstring sections**: Example→Пример, Resources→Ресурсы, Prompts→Промпты, Data features→Модули данных
- **kad_arbitrazh**: 24 English codes → Russian transliteration
- **cbrf**: key_rate → klyuchevaya_stavka
- **publikatsii**: paid service → платный сервис
- 680 tests passed; ruff check/format clean

## My-RU-Coverage: round #39 — industry terminology russification

One commit (187 insertions, 23 files) replaces 7 anglicisms with Russian equivalents:

| Anglicism | Russian replacement |
|-----------|-------------------|
| конгломерат | холдинг |
| финтех | финансовые технологии |
| маркетплейсы | торговые площадки |
| продуктовый ритейл | продуктовая розница |
| девелопмент | застройка |
| проптех | имущественные платформы |
| омниканальные | многоканальные |

Theme tags, file names, cross-references, and the network graph are all updated. INDUSTRY_TRANSLATION registry updated to round #39.

## codex-console-english: ~182 translation artifact fixes

One commit (256 insertions, 44 files) corrects approximately 182 translation artifacts across the entire codebase:

- **OTP terminology**: inconsistent one-time password references standardized
- **obtain → get**: more natural English phrasing
- **topic → subject**: correct mailing-list terminology
- **Verification → Validation**: domain-accurate usage
- Plus numerous smaller consistency fixes across services, routes, templates, and JavaScript

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
