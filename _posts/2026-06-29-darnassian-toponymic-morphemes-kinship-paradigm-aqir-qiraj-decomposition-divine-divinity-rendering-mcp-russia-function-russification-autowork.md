---
title: "AUTOWORK - WoW: Darnassian toponymic morphemes (Aran, -naar, -thalas), 2×2 kinship paradigm, -relos third attestation, Zandali-Elven cognate candidates, Aqir -qiraj decomposition (-qir + -azj), N'- prefix cross-language; Divine Divinity overlay rendering + NPC dialog; MCP-Russia function/test russification; RU-Coverage rounds #50–51; ru-skill rounds #66–67; tg_summarizer PromptManager + S3 alarm; codex-console final artifacts"
date: 2026-06-29
layout: post
---

**[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** receives six commits of deep linguistic analysis: Darnassian gains 34 place names revealing toponymic morphemes (*Aran* = "town", *-naar* = "settlement", *-thalas* = "home/realm"), a 2×2 kinship paradigm hypothesis (*-da/-do × -na/-nar*), the third *-relos* attestation from *elen'relos*, and three new confirmed phrases. The *-da* suffix is now identified as the first shared grammatical morpheme between troll and elven language families (Investigation 6), and three additional Zandali–Elven cognate candidates are analyzed (Investigation 7). Alien comparative introduces the *-qiraj* decomposition (*-qir* + *-azj*) — potentially the first Aqir morpheme with reflexes in all three descendant languages — and the *N'-* prefix as a possible fourth Aqir substrate morpheme. **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds overlay tile rendering, object sprite catalog bridge, and NPC dialog text integration (728 tests). **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies function names (*_parse→_razobrat*, *get→poluchit*), cache methods, dictionary keys, and ~28 test classes / ~139 test functions. Plus My-RU-Coverage rounds #50–51, ru-skill rounds #66–67, tg_summarizer PromptManager + S3 alarm, and codex-console final artifact sweep.

## wow_constructed_languages: Darnassian toponymic morphemes and 34 place names

One commit (208 insertions, 16 deletions) adds 34 proper nouns from warcraft.wiki.gg, revealing three recurring toponymic morphemes and a full Investigation 8:

### Toponymic Morphemes (Investigation 8)

| Morpheme | Attestations | Inferred Meaning | Confidence |
|----------|-------------|-------------------|------------|
| *Aran* | Ameth'Aran, Bashal'Aran, Loreth'Aran, Morlos'Aran | "Town / settlement" | Moderate |
| *-naar* | Astranaar, Dolanaar, Sylvanaar | "Town / settlement" | Moderate |
| *-thalas* | Eldre'Thalas, Nar'thalas, Quel'Thalas (Thalassian) | "Home / realm" | Moderate–High |

*Aran* vs. *-naar*: Both appear to mean "town/settlement" but differ phonologically. The preferred hypothesis is **allomorphy** — *Aran* is the free form, *-naar* is the reduced suffix form, with initial vowel absorption and consonant metathesis in suffix position. Cross-elven significance: *-thalas* "home/realm" is shared with Thalassian (*Quel'Thalas* = "High Home"), confirming it as a Proto-Elven toponymic morpheme.

Notable new proper nouns: *Elune'ara* (lake in Moonglade), *Elune'eth* (district in Suramar), *Shala'nir* (druid grove containing the *Shal* root also in *Shal'nar*/*Shal'na*), *Thal'dranath* (original name of Broken Shore, containing *Thal* "home").

### Three new confirmed phrases

| Phrase | Translation | Source |
|--------|-------------|--------|
| *Ande'thoras-ethil* | May your troubles be diminished | Warcraft Encyclopedia |
| *Anu'dorini Talah* | Let my will be known | Warcraft III (Malfurion) |
| *Bandu Thoribas* | Prepare to fight | Warcraft Encyclopedia |

*Ande* extends the jussive/imperative system (*Andu*, *Tor*, now *Ande* — possibly optative/wish mood). *Bandu* shares the *-du* element with *Andu*, suggesting a shared jussive root. *Anu'dorini Talah* provides evidence for subject-initial word order in declarative/performative utterances.

---

## wow_constructed_languages: 2×2 kinship paradigm and -relos third attestation

One commit (20548 insertions, 46 deletions) adds three major linguistic investigations:

### Investigation 5: *-relos* — Third attestation from *elen'relos*

The element *-relos* now has three independent attestations:

| Compound | First Element | *-relos* |
|----------|---------------|----------|
| *Belor'relos* | *belor* (sun) | "Sun-caller" |
| *Anu'relos* | *anu'* (the) | "The caller" |
| *elen'relos* | *elen* (star/divine?) | "Star-caller" |

With three attestations, *-relos* = "caller" becomes the first attested Darnassian **agentive morpheme** at Moderate confidence. The doubled /r/ in *Belor'relos* vs. single /r/ in *Belore'dorei* may mark morphologically conditioned gemination — agentive compounding vs. descriptive compounding.

### Investigation 2 extended: 2×2 kinship paradigm

If *-nar* in *Shal'nar* (aunt) represents *-na* + *-r*, the final /r/ could mark the formal register of collateral kinship:

| | Informal | Formal |
|---|---|---|
| **Parent** | *-da* (*An'da*, *Min'da*) | *-do* (*Minn'do*, *Shan'do*) |
| **Collateral** | *-na* (*Shal'na* in Thalassian) | *-nar* (*Shal'nar* in Darnassian) (?) |

The paradigm makes a clear, falsifiable prediction: future collateral kinship terms should end in *-na* (informal) or *-nar* (formal).

### Other advances

- **Nerubian**: *tikk* (from scroll text *Unhhh-tikk-a-shisss*) connected to *tak-* element as sixth attestation, bridging combat and ritual contexts. Initial-apostrophe names (*Y'tekhi*, *A'zak*, *Ix'lar*, *Ix'zek*) identified as potential Shath'Yar substrate.
- **Thalassian**: *Bin dorei am'ovel* analyzed as second *am'* pronoun attestation. *Band'or shorel'aran* upgraded to confirmed (Chinese WoW official translation). RPG/speculative etymology section added (*Quel'Zaram* = "High blade", *Ronae* = "Peaceful").
- **Zandali**: *-da* kinship suffix cross-family cognate with elven languages (Investigation 6).

---

## wow_constructed_languages: Zandali-Elven cognate candidates

One commit (375 insertions, 20 deletions) adds Investigation 7 — the first systematic search for additional cognates between troll and elven language families:

| Candidate | Correspondence | Confidence | Key Problem |
|-----------|---------------|------------|-------------|
| *-da* kinship suffix | Shared suffix | Low–Moderate | Baby-talk convergence possible |
| *\*ala-* "bright/burning" | Zandali *Alai* "fire" ↔ Elven *alah* "light" | Low–Moderate | Convergent association |
| *na* preposition | Shared grammatical morpheme | Low–Moderate | Short CV prepositions universally common |
| *na/no* pair | Structural parallel | Low | Functional mapping imperfect |
| *Ma'/Min'* "mother" | Conditioned sound change | Low | Counterexamples show irregularity |

**Overall assessment**: The strongest case comes from the **convergence of multiple weak signals** — three independent morphemes with Low–Moderate confidence each provide a pattern consistent with deep genetic relationship at ~16,000 years of divergence.

Also added: *-ar* loanword analysis in Haranir vocabulary, expanded Greenspeaker/Thornspeaker section, cross-cultural druidic vocabulary table, and Alai/alah cross-references between Zandali and Darnassian.

---

## wow_constructed_languages: Aqir -qiraj decomposition and N'- prefix

The same commit adds two major advances in alien comparative linguistics:

### The *-qiraj* Decomposition: *-qir* + *-azj*

If *-qiraj* = *-qir* + *-azj*, then *Ahn'qiraj* = "Old/Sacred [realm of the] Qir" — and *-azj* would be the same Aqir morpheme as nerubian *Azj-* (prefix) and naga *Nazj-* (if *Nazj-* = *N-* + *Azj-*). All three share the final sequence /ɑːʒ/, which is unlikely to be coincidental.

| Language | Morpheme | Position | Attestation |
|----------|----------|----------|-------------|
| Nerubian | *Azj-* | Prefix | *Azj-Kahet*, *Azjol-Nerub* |
| Naga | *Nazj-* | Prefix | *Nazjatar* (if *N-* + *Azj-*) |
| Qiraji | *-azj* | Suffix | *Ahn'qiraj* (if *-qir* + *-azj*) |

If confirmed, *Azj-*/**-azj*** would be the **first Aqir morpheme with reflexes in all three descendant languages**. The dual distribution (prefix in nerubian/naga, suffix in qiraji) parallels the *tak-*/**-tak*** distribution in nerubian and may reflect a systematic Aqir morphological feature.

### The *N'-* Prefix: A Fourth Aqir Substrate Morpheme?

The Shath'Yar *N'-* prefix ("negation/void/absence" in *N'Zoth*, *N'raqi*) may have reflexes in naga (*Nazj-* = *N-* + *Azj-*, "hidden realm") and possibly nerubian (*Nezar'Azret*). If confirmed, this would be a fourth Aqir substrate morpheme — but the Egyptian design aesthetic confound makes nerubian evidence weak. **Confidence: Very Low–Low**.

---

## open-divine-divinity-rust-bevy: Overlay rendering and NPC dialog

Two commits (1,102 insertions, 91 deletions, 11 files) advance the game engine from data parsing to visual rendering:

- **CPacked imagelist tile rendering**: Parse and render tiles from packed image lists, dialog text integration from GameTextAssets, enhanced world object placement from location data, companion hint refinement
- **Overlay tile rendering**: Store overlay_tile_ids in MapLayout, spawn semi-transparent overlay sprite layer above floor tiles with real-texture and placeholder fallback
- **Object sprite catalog bridge**: Animation_index from object catalogue, look up obj_{anim_index} sprites before semantic key fallback
- **NPC dialog integration**: spawn_npcs checks GameTextAssets for NPC-matching dialog trees, uses text-derived dialog when found
- **6 new tests** (722 → 728 total)

---

## mcp-russia: Function name and test russification

Two commits (650 insertions, 515 deletions, 78 files) perform the deepest code-level russification yet:

### Function and method names

| English | Russian | Scope |
|---------|---------|-------|
| `_parse` | `_razobrat` | All data modules |
| `get` | `poluchit` | Cache methods |
| `set` | `ustanovit` | Cache methods |
| `clear` | `ochistit` | Cache methods |
| `_fallback` | `_rezerv` | Feature module |
| `_auth_note` | `_zametka_ob_avtorizatsii` | Redator resources |

### Parameters and constants

`package_name`→`imya_paketa`, `short_name`→`korotkoe_imya`, `root_server`→`kornevoy_server`, ЦИК resource keys russified

### Dictionary keys and test names

`deficit`→`defitsit`, `value`→`znachenie`, `fias_id`→`identifikator_fias`, `ip_end`→`okonchanie_ip`, `status`→`sostoyanie` (3 modules). ~28 test classes and ~139 test function names russified across 24 test files. Typos fixed: `_normlizovat`→`_normalizovat`, `analise`→`analiz`.

---

## My-RU-Coverage: Rounds #50 and #51

Two commits (914 insertions, 809 deletions, 88 files) continue MOEX analyst report loanword russification:

### Round #50

- **сервис→услуга**: ~100 occurrences across 28 reports, directory renamed "Интернет-информационные сервисы" → "услуги"
- **Описание бизнеса→Описание деятельности**: 42 reports + scripts
- **JSON key russification**: build_network.py (узлы/связи/имя/упоминания/вес...), update_enrichment.py (описание/цепочка_поставок/клиенты_и_поставщики)
- **тендер→торги** (APTK)

### Round #51

| Loanword | Russian replacement | Reports affected |
|----------|-------------------|-----------------|
| workflow | рабочий процесс | multiple |
| программатик | автоматизированная покупка рекламы | MOEX |
| офшорная | прибрежная | banking |
| контент | содержимое | media |
| клиентские | клиентов | telecom |
| рейтинговые | оценки кредитоспособности | financial |
| корпоративные | для предприятий (не-финансовые) | analytics |

JSON keys russified in moex_blue_chip_queue.py; WIKILINK_ALIASES expanded by 4 entries.

---

## ru-skill: Documentation russification rounds #66–67

Two commits (474 insertions, 273 deletions, 45 files):

### Round #66

*skill*→*навык*, *public API*, *fuzzy search*, *websocket*, *setup*→*настройка*, *secrets-файл*→*файл секретов*, *package path*→*путь пакета*, *iteration backlog*→*перечень задач следующей итерации*, ~30 other English jargon terms. Doc-regression expanded (round 66).

### Round #67

*Гайд*→*Руководство* (16 h1 headings + 34 links), *skill-каталоги*→*каталоги навыков*, *secrets-шаблон*→*шаблон секретов*, *мержится*→*вливается*, *legacy standalone*→*устаревший*, *API key*→*API-ключ*, *Slug/Слаг*→*Идентификатор*, *runtime*→*среда выполнения*, *issue tracker*→*система отслеживания задач*, *Boolean*→*булевый*, *логин*→*вход*. Doc-regression expanded (round 67).

---

## tg_summarizer: PromptManager, S3 alarm, NLP guard

Two commits (737 insertions, 158 deletions, 23 files):

- **PromptManager**: Update prompt for configurable refresh cycles
- **S3 upload alarm**: CloudWatch alarm for failed S3 uploads
- **Coverage dedup EMF**: Remove duplicate coverage metrics in EMF output
- **Compact NLP prompt**: Token savings in NLP processing prompts
- **Circuit breaker NLP guard**: Prevent cascading failures from NLP service errors
- **Meta-artifacts stripping**: Expanded strip patterns (стоит/следует/важно отметить, подводя итог, резюмируя)
- **Dead code removal**: Removed unused telegram_client.py functions
- **178 new tests** (363 → ~541 total)

---

## codex-console-english: Final artifact sweep

One commit (40 insertions, 16 deletions, 12 files): ~15 remaining Chinese-English artifacts fixed — *the X of Y*→possessive form, CSS header labels, awkward docstrings in payment/registration/task modules. All tracked files now confirmed fully English (Round 53).

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
