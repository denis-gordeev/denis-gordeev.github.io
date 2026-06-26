---
title: "AUTOWORK - WoW: Major Thalassian expansion — 17+ confirmed words, kinship terms, battle cry formulae, 20+ untranslated phrases; Shath'Yar open investigations; Divine Divinity world/level parsing; MCP-Russia MetaFunktsii russification; RU-Coverage rounds #47–48; codex-console artifact sweep; tg_summarizer warmup & retry; ru-skill doc russification"
date: 2026-06-26
layout: post
---

**[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** receives its largest Thalassian update: 17+ confirmed words (including *Felo* = "flame", *Thas* = "forest", *Arihana* = "magic"), three kinship terms (*Ann'da* = "Papa", *Minn'da* = "Mama", *Shal'na* = "Aunt"), 20+ untranslated phrases, battle cry formulae, and expanded syntax analysis. Shath'Yar gains three Open Linguistic Investigations (*za* "place" vs. "my", *ma* copula vs. "millennia", *iilth/ilith/illith* pronoun variants). **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds world.x partition parsing, location coordinate tables, and an objects catalogue (1,790 lines, 47 tests). **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies all MetaFunktsii fields, settings constants, error keys, and *Data→Dannye* classes. Plus My-RU-Coverage rounds #47–48, codex-console artifact sweeps, tg_summarizer Lambda warmup, and ru-skill documentation russification.

## wow_constructed_languages: Major Thalassian expansion

Two commits (1,155 insertions, 229 deletions, 20 files) transform Thalassian from a handful of confirmed words to a language with a rich vocabulary, kinship terminology, and syntactic analysis grounded in Blizzard-confirmed translations.

### 17+ confirmed words

All words are attested in official sources (Warcraft Encyclopedia, Sean Copeland Twitter posts, novels, in-game quests):

| Word | Translation | Key Attestation |
|------|-------------|-----------------|
| *Shindu* | Failing, Breaking | *Lament of the Highborne* |
| *Selama* | Justice | Warcraft Encyclopedia |
| *Tal* | Death | Tempest Keep (Solarian) |
| *Felo* | Flame | *Felo'melorn* = "Flamestrike" (Arthas: Rise of the Lich King) |
| *Thas* | Forest | *Thas'alah* = "Light of the Forest" (Tales of the Hunt) |
| *Arihana* | Magic | Sean Copeland (Twitter) |
| *Alann* | Heart | Sean Copeland (Twitter) |
| *Anore* | People, Our people | Warcraft Encyclopedia |
| *Jael* | Rat | Quest: *Kim'jael Indeed!* |
| *Fallah* | Breaking through | *Lament of the Highborne* |
| *Aranal* | Rise | Sean Copeland (Twitter) |
| *Shala* | Safe | Warcraft Encyclopedia |
| *Rea* | And | Sean Copeland (Twitter) |
| *No* | To, All | Tempest Keep / *Lament of the Highborne* |

### Kinship terms with suffix *-da*

Three confirmed kinship terms share the *-da* suffix:

| Word | Translation | Source |
|------|-------------|--------|
| *Ann'da* | Papa, Father | *Descent* (novel) |
| *Minn'da* | Mama, Mother | *Descent* (novel) |
| *Shal'na* | Aunt | Quest: *What Might Come* |

*Ann'da* and *Minn'da* differ only in their initial element, suggesting a prefix + suffix structure where the prefix encodes the specific relationship and *-da* marks "parent." *Shal'na* uses *-na* instead, possibly marking a different generation level or gender.

### Confirmed phrases with Blizzard translations

The expanded corpus now includes fully categorized confirmed phrases:

- **Greetings**: *Bal'a dash* ("Greetings"), *Shorel'aran* ("Farewell"), *Sinu a'manore* ("Well met"), *Al diel shala* ("Safe travels"), *Doral ana'diel?* ("How fare you?")
- **Blessings**: *Anar'alah belore* ("By the light of the sun"), *Ande'thoras-ethil* ("May your troubles be diminished"), *Elu'meniel mal alann* ("May peace calm your heart"), *Ama noral'arkhana* ("Saved by magic")
- **Battle cries**: *Selama ashal'anore* ("Justice for our people"), *Shindu fallah na!* ("They are breaking through!"), *Bash'a no falor talah!* ("Taste the chill of true death!")

### Battle cry formulae

Three battle cry patterns are now identified:

1. **[Noun] + [Verb] + [Particle]**: *Shindu fallah na!* ("They are breaking through!")
2. **[Noun] + [Prepositional phrase]**: *Selama ashal'anore* ("Justice for our people")
3. **[Imperative] + [Object]**: *Bash'a no falor talah!* ("Taste the chill of true death!")

*Selama* appears in three variant forms (*ashal'anore*, *am'oronor*, *amor'anore*), functioning as a battle cry template.

### Expanded syntax analysis

The expanded corpus provides three independent examples consistent with **SVO/SV word order**:

- *Anu belore dela'na* = "The sun will guide us" → Subject + Verb
- *Shindu fallah na* = "They are breaking through" → Subject + Verb + Particle
- *Doral ana'diel?* = "How fare you?" → Question Word + Verb

The optative construction is confirmed with two examples: *Ande'thoras-ethil* (intransitive) and *Elu'meniel mal alann* (transitive with explicit object).

### Compound names confirmed

| Name | Translation | Decomposition |
|------|-------------|---------------|
| *Felo'melorn* | Flamestrike | *Felo* (flame) + *'melorn* (strike) |
| *Thas'alah* | Light of the Forest | *Thas* (forest) + *'alah* (light) |
| *Thas'dorah* | Valor of the Forest | *Thas* (forest) + *'dorah* (valor) |
| *Kim'jael* | Little rat | *Kim* (little?) + *'jael* (rat) |

### 30+ proper nouns and 20+ untranslated phrases

The vocabulary now includes structured sections for ethnonyms (*Belore'dorei* = "Child of the Sun"), places (Quel'Thalas, Quel'Danas, Elrendar, etc.), Sunwell Gates (Agamath, Rohendor, Archonisus), and items (Felo'melorn, Thori'dal, Rae'shalare). Twenty-two untranslated phrases from in-game dialogue are catalogued with speaker/context.

---

## wow_constructed_languages: Shath'Yar Open Linguistic Investigations

One commit (307 insertions, 25 deletions) adds three structured investigations to Shath'Yar grammar:

### Investigation 1: *za* — "Place" vs. "My" (Possessive)

The morpheme *za* appears with two incompatible glosses. New evidence from the wiki identifies *ifis* = "(of) my" from *Uulwi ifis halahs* = "The shadow of my corpse." If *ifis* is a genuine possessive, then *za* may be exclusively "place" — though *za awtgsshu* = "My whispers" resists this interpretation. Three hypotheses are evaluated (homophonous morphemes, grammaticalized possessive, *ifis* resolves the ambiguity). **Confidence: Low–Moderate.**

### Investigation 2: *ma* — Copula vs. "Millennia"

The morpheme *ma* functions as both a free copula (*Ywaq ma phgwa'cul* = "They are the whisper") and a bound temporal root (*Uulg'ma* = "After millennia"). The syntactic position reliably distinguishes them: free *ma* = copula, bound *ma* = temporal. **Confidence: Moderate** for two homophonous morphemes.

### Investigation 3: *iilth* vs. *ilith* vs. *illith* — Three Forms for "You"

Three variant forms of the 2nd person singular pronoun are attested across different speaker types:

| Form | Speaker Type | Source |
|------|-------------|--------|
| *iilth* | Faceless commanders (N'raqi) | Volazj, Kaahrj, Zon'ozz, G'huun |
| *ilith* | N'Zoth's direct servant | Yor'sahj |
| *illith* | Aquatic entity | Vol'zith the Whisperer |

The allophonic analysis is most parsimonious: *iilth* with a long vowel, *ilith* from vowel reduction in fast speech, and *illith* from consonant gemination in whispered/hissed aquatic speech. **Confidence: Moderate.**

---

## open-divine-divinity-rust-bevy: World/Level data parsing

One commit (1,790 insertions, 3 deletions, 6 files) implements three binary format parsers reverse-engineered from the OpenDivine project documentation:

- **world_data.rs**: Parses world.x0–x4 paged cell-grid files (1,024 sectors, 512 cells each, floor/overlay tiles, object placements)
- **location_data.rs**: Parses location.000/001/002 named coordinate tables (Story, Traps, Generation sub-tags)
- **objects_catalog.rs**: Parses objects.000 global catalogue (148-byte records, 7,208 entries, door/chest/lever/key flags)

Adds `MapLayout::from_world_partition()` to convert parsed world data into the existing map layout system. All parsers auto-discover from the game installation and gracefully degrade when absent. **47 new tests** (632 → 679 total).

---

## mcp-russia: Deep code-level russification

One commit (2,342 insertions, 407 deletions, 59 files) performs the deepest russification pass yet:

- **MetaFunktsii fields** (8 fields, ~199 replacements in 28 files): `name`→`imya`, `description`→`opisanie`, `version`→`versiya`, `api_base`→`baza_api`, `requires_auth`→`trebuet_autentifikatsii`, `auth_env_var`→`peremennaya_avt_env`, `enabled`→`vklyuchena`, `tags`→`tegi`
- **Settings constants** (9 constants, 34 replacements in 11 files): `HTTP_TIMEOUT`→`TAIMAUT_HTTP`, `HTTP_MAX_RETRIES`→`MAKS_POVTOROV_HTTP`, `HTTP_BACKOFF_BASE`→`BAZA_EKSPON_ZADERZH`, `USER_AGENT`→`POLZOVATELSKIY_AGENT`, `TOOL_SEARCH`→`POISK_INSTRUMENTOV`, etc.
- **Dictionary keys**: `"error"`→`"oshibka"` (22 replacements in 5 modules + tests)
- **Function parameters**: `postal_code`→`pochtovyy_indeks`, `max_requests`→`maks_zaprosov`, `max_retries`→`maks_povtorov`, `tool_name`→`imya_instrumenta`, `module_path`→`put_modulya`
- **Class renames**: `*Data`→`*Dannye` (8 classes), `McpRussiaError`→`OshibkaMcpRussia`

---

## My-RU-Coverage: Rounds #47 and #48

Two commits (293 insertions, 199 deletions, 48 files) continue the loanword russification of MOEX analyst reports:

### Round #47

| Loanword | Russian replacement | Reports affected |
|----------|-------------------|-----------------|
| сегмент | сектор/сфера/направление | 20 |
| листинг | допуск к торгам | MOEX ×3 |
| инвестиционно-банковский | услуги по размещению и торговле ценными бумагами | VTBR ×3 |
| клиентский | абонентский/пользовательский/покупателей | 4 ×7 |
| POS | устранение | T |

### Round #48

| Loanword | Russian replacement | Reports affected |
|----------|-------------------|-----------------|
| экосистема/экосистемные | совокупность сервисов/сопутствующие сервисы платформы/сервисный контур | 11 |
| IPO | первичное публичное размещение | 4 |
| ERP/EPC/DDoS | устранение | 4 |
| аудит | проверка | scripts |

---

## codex-console-english: Two artifact sweeps

Two commits (214 insertions, 160 deletions, 38 files) fix ~142 Chinese-English translation artifacts total:

- **~118 artifacts**: *X failed*→*Failed to X*, *configuration*→*settings*, *information*→*details*, *successfully*→simple past tense
- **~24 remaining artifacts**: bare *skip*→*skipping*, *API return data*→*response*, *No available*→*No*, awkward UI phrasing

---

## tg_summarizer: Lambda warmup, Telegram retry, prompt brevity

One commit (262 insertions, 11 deletions, 8 files):

- **Lambda warmup**: warmup event flag + `WarmupScheduleExpression` parameter to keep Lambda containers hot
- **Telegram reconnection retry**: exponential backoff in `start_clients()` for resilient long-polling
- **Prompt brevity rule**: *"без вводных слов и оборотов"* added to both summary prompts
- **Meta-artifacts expansion**: strip patterns now include *стоит/следует/важно отметить*, *подводя итог*, *резюмируя*
- **Template fix**: `template.yaml` Outputs indentation corrected (was nested in Resources)
- **18 new tests** (total 363)

---

## ru-skill: Documentation russification

One commit (346 insertions, 300 deletions, 4 files): ~120+ English jargon terms replaced in README.md, docs/roadmap.md, and TODO.md with Russian equivalents (*user-facing*→*пользовательский*, *doc-regression*→*документная регрессия*, *heading scheme*→*схема заголовков*, *install-flow*→*поток установки*, *publishable*→*опубликованный*, *domain-inherent*→*обусловлен доменом*, *frontmatter*→*вводные метаданные*, etc.).

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
