---
title: "AUTOWORK - WoW Rounds 24-25 + Investigation 10, Divine Divinity dynamic walkability, MCP-Russia round 64, RU-Coverage rounds 59-60, ru-skill round 76, tg_summarizer cost widget"
date: 2026-07-05
layout: post
---

Seven repositories see new commits on July 4: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Rounds 24-25 plus Investigation 10 with Shath'Yar expanding to 94+ coded phrases and auxiliary inversion under temporal fronting, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds dynamic walkability revalidation for in-flight paths, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies shared infrastructure in round 64, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships rounds 59-60, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 76, and **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds UPDATE_SUMMARY cost optimization and cost-by-call-type widget.

## wow_constructed_languages: Rounds 24-25, Investigation 10 — Shath'Yar 94+ phrases, auxiliary inversion, og homophony, -ka privative

Three commits (1956 insertions, 48 deletions, 28 files):

### Round 24 — 17 new Shath'Yar phrases (77+ → 94+), gul'kafh polysemy, sythn dual function

- **gul'kafh polysemy** (Investigation 6): "to corrupt" vs. "to summon" — two distinct senses attested across in-game phrases; morphological decomposition *gul'* = "rotting" + *kafh* = "to summon/bring forth"
- **sythn dual function** (Investigation 7): "to serve" (verb) vs. "servant" (noun) — zero-derivation nominalization, supported by 4+ attestations in both syntactic positions
- **Zandali cross-reference**: *no* connective linked to elven-comparative correspondence table; Bwon' investigation updated with new data
- 17 confirmed coded phrases added; total vocabulary now 94+

### Round 25 — og homophony (Inv 8), -ka privative (Inv 9), Ma'/Min' glottal conditioning falsified

- **og homophony** (Investigation 8): *og* = existential particle ("there is/are") vs. *og* = preposition ("in/inside") — homophony rather than polysemy; distinct syntactic distributions confirmed
- **-ka privative** (Investigation 9): suffix *-ka* marks absence/privation in Shath'Yar — *n'zilka* = "without master", parallel to English *-less*; 3+ attestations
- **Ma'/Min' glottal conditioning falsified**: proposed rule that glottal stop conditions Ma'/Min' alternation rejected; no phonological environment predicts the alternation
- Darnassian grammar expanded with new phonological evidence

### Investigation 10 — Difficult phrase reanalysis, auxiliary inversion, mar- prefix

- **Auxiliary inversion under temporal fronting**: Adv-Aux-S-V word order identified when temporal adverb fronts — extends previously attested locative fronting to a general topic-fronting strategy
- **qwor = 'above/over'**: preposition with 2 attestations in spatial phrases
- **lal = 'new'/perfective**, **arwi = 'all/again'**, **ga' = 'rotting'**: new vocabulary items from partial translations
- **mar- = 'corrupt/dark'** prefix: extracted from previously untranslated phrases; parallels *gul'* semantic field
- Possessed-Possessor alternative genitive order (inalienable possession?) noted for further investigation
- 6 new speculative dictionary entries; investigation count updated 7 → 10

---

## open-divine-divinity-rust-bevy: Dynamic walkability, in-flight path revalidation

One commit (211 insertions, 12 deletions, 2 files):

- **WalkabilityChanged event**: fires when `update_walkability_on_open` changes a tile's walkable state (doors/chests/levers toggled)
- **revalidate_move_paths system**: recalculates in-flight `MovePath` when walkability changes near the player — prevents entities from walking through newly blocked tiles
- **Movement system registration**: `set_player_move_target` and `move_player_towards_target` systems now properly registered in the Bevy schedule
- 6 new tests (785 → 791 total)

---

## mcp-russia: Round 64 — Shared infrastructure russification

One commit (5483 insertions, 1228 deletions, 72 files):

- **_shared/ type aliases**: ToolFn→TipFunktsiiInstrumenta, registry→reyestr, base→baza, pkg→paket, mod→modul, fn→funktsiya, sig→signatura
- **Server variables**: server_obj→obiekt_servera, auth_info→svedeniya_ob_avtorizatsii, registry→reyestr
- **Data module constants**: DADATA_SUGGEST_URL→DADATA_URL_PODSKAZOK, PKK_API_BASE→PKK_BAZA_API
- **Data module variables**: bills→zakonoproekty, votes→golosovaniya_spisok, history→istoriya, restrict→ogranicheniya, orgs→organizatsii, valute_data→dannye_valyut, rights→prava
- **cekrf HTML parser**: _in_td→_v_yacheyke_dannykh, _in_th→_v_yacheyke_zagolovka
- **kad_arbitrazh**: _raw→_syranye/_syraya
- **Tests**: client→klient fixture, 4 classes, 20 functions, ~150+ variable renames
- **Docs**: features.md, analiz-zakonodatelstva.md, zhurnalist-stati.md, CONTRIBUTING.md updated

---

## My-RU-Coverage: Rounds 59-60

Two commits (309 insertions, 234 deletions, 28 files):

### Round 59

| Category | Change |
|----------|--------|
| фокус→акцент | 4 reports |
| Legacy→исторический | CLAUDE.md, LEGACY.md |
| {Industry}→{Отрасль} | Template replacements |
| AI серверы→серверы ИИ | Tech term correction |

### Round 60

| Category | Change |
|----------|--------|
| транзакция→расчётная операция | Financial terminology |
| Latin wikilinks→Cyrillic | [[Ozon Банк]]→[[Озон Банк]], [[Kaspersky]]→[[Касперский]] |
| партнёр→контрагент | 20 occurrences across 13 reports |
| топ→тройка крупнейших | Corporate ranking terminology |

---

## ru-skill: Round 76 — Package README and SKILL.md russification

One commit (94 insertions, 83 deletions, 30 files):

- **Package READMEs**: API-справочник→Справочник API, CI→система непрерывной интеграции across 15+ packages
- **SKILL.md files**: CMS→шаблон CMS, CLI→интерфейс командной строки, SSR→серверный рендеринг, dotenv→конфигурация окружения; ~10 files updated
- **Tests**: skill-docs.test.js — 40 lines updated with translated test labels and descriptions
- **Roadmap**: docs/roadmap.md expanded with new milestones

---

## tg_summarizer: UPDATE_SUMMARY cost optimization, cost-by-call-type widget

One commit (186 insertions, 9 deletions, 9 files):

- **UPDATE_SUMMARY cost optimization**: reduces Lambda invocations by batching summary updates
- **Cost-by-call-type widget**: OpenAI EMF dimension for per-call-type latency and cost breakdown
- **Meta-artifacts expansion**: additional metadata captured for observability
- 130+ new tests (digest post-processing: 70 lines, lambda handler: 60 lines)

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
