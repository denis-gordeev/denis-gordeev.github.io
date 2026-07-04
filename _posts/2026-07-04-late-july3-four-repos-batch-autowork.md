---
title: "AUTOWORK - WoW Round 23, MCP-Russia identifier russification, ru-skill round 75, tg_summarizer cost optimization"
date: 2026-07-04
layout: post
---

Four repositories have late-July-3 commits not covered in the previous batch: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Round 23 with Shath'Yar expanding to 77+ coded phrases and a negative existential copula hypothesis, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies remaining English identifiers across shared and data modules, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 75 with SKILL.md and package README updates, and **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds NLP cost optimization and EMF metrics.

## wow_constructed_languages: Round 23 — Shath'Yar 77+ phrases, negative existential copula *En'*, Zandali *no*/*na* split, Darnassian quantitative confirmation

One commit (539 insertions, 14 deletions, 12 files):

### Shath'Yar — 14 new coded phrases (63+ → 77+)

- **SVO**: *H'iwn zaix Shuul'wah* = "All praise Deathwing"; *Il'zarq taag ov'kadaq* = "It sings of unspeakable horrors"
- **S-Aux-V-O**: *Iilth qi mah'shar fhn oorql N'Zoth!* = "You will be the first of many to glimpse the madness of N'Zoth!"
- **PP-S-V (temporal fronting)**: *Uulg'ma, ag qam* = "After millennia, we have returned" — extends pragmatic fronting from locative to temporal, confirming a general topic-fronting strategy
- **PP-V-O (locative + imperative)**: *Shkul an'zig qvsakf KSSH'GA, ag'THYZAK agthu!* = "From its BLEAKEST DEPTHS, we RECLAIM this world!"
- **S-Copula-Pred**: *Yoq'al shn ky ywaq nuul* = "It is the perpetuity in which they dwell" — potentially first attested relative clause (juxtaposed, no overt relativizer)

### Negative existential copula *En'*

- *En'othk uulg'shuul* = "There is no light after death" — *En'* = negative existential copula, *othk* = "light"
- Creates a copula paradigm: affirmative *ma*, negative existential *En'*, existential particle *og*
- Distinction parallels English "There is no light" (copular) vs. "No light" (particle)
- Confidence: Low–Moderate; compound noun alternative (*En'othk* = "darkness") not ruled out

### Zandali *no* vs *na* functional split

- *na*: 5+ attestations, pre-nominal, confirmed locative/allative/genitive, common and proper nouns
- *no*: 3+ attestations, between proper nouns only, loa-title connective (dedicatory/vocative)
- Three analyses: (1) unrelated particles, (2) vowel-conditioned allomorphy (counterexample: *no Shadra*), (3) functional split from Proto-Troll-Elven ancestor
- Complementary distribution supports functional specialization; Confidence: Low–Moderate

### Darnassian *Aran*/*-naar* quantitative confirmation

- Complete inventory verified: 8 *Aran* (100% consonant-final stems), 4 native *-naar* (100% vowel-final stems), 1 borrowed *-naar* (*Satyrnaar*)
- Phonological conditioning exceptionless across 12 native stems; Fisher's exact test p < 0.01

---

## mcp-russia: Identifier russification across shared infrastructure and data modules

One commit (1298 insertions, 1215 deletions, 69 files):

- **Shared modules**: status→sostoyanie, result→rezultat, text→tekst, name→imya/nazvanie, key→klyuch across batch.py, feature.py, http_client.py
- **Data modules**: cbrf, cekrf, fssp, gosduma, kad_arbitrazh, rosapi, rosaudit, sovfed, zakupki, deloproizvodstvo
- **Tests**: all 60+ test files updated with new Russian identifiers
- **Discovery and root server**: meta→metadannye, server→server_fn, name→imya, result→rezultat

---

## ru-skill: Round 75 — Package README + SKILL.md + test regressions

One commit (172 insertions, 100 deletions, 31 files):

- **Package READMEs**: серверно отрендеренных→сгенерированных на сервере, трекинг-параметров→параметров отслеживания, Парсинг→Разбор, Эндпоинт→Конечная точка, CLI→интерфейс командной строки (yandex-market-search, kinopoisk-search, stoloto-lotto, moex-shares, pravo-documents, yandex-rasp, toss-securities)
- **SKILL.md files**: целевой трек→целевое направление (daiso-product-search), cookie→куки (delivery-tracking), CMS-шаблон→шаблон CMS (mchs-storm-warnings), CLI-обёртках→обёртках командной строки (zipcode-search), английский-первый→русский-первый (kakaotalk-mac); ~15 more files with targeted fixes
- **Tests**: skill-docs.test.js — 6 English comments and 1 test name translated; round 75 regressions added
- **README.md**: yandex-market-search table synchronized with current packages and migration

---

## tg_summarizer: NLP cost optimization, CallType EMF, CbFiltered metric

One commit (189 insertions, 42 deletions, 9 files):

- **NLP_CHECK_MAX_INPUT_CHARS**: 2000→500 (~75% input cost reduction)
- **CallType dimension**: added to OpenAI EMF for per-call-type latency breakdown
- **CbFiltered metric**: new metric in NLP filter EMF for circuit breaker rejection visibility
- 17 new tests (total 514)

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
