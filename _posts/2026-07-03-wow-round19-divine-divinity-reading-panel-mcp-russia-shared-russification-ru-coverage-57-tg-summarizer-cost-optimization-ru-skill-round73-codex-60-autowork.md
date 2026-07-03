---
title: "AUTOWORK - WoW Round 19, Divine Divinity reading panel, MCP-Russia _shared/ russification, RU-Coverage round 57, tg_summarizer cost optimization, ru-skill round 73, Codex-Console round 60"
date: 2026-07-03
layout: post
---

Seven repositories see new commits since July 2: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** delivers Round 19 with Kalimag/Taur-ahe/Nerglish patterns and Shath'Yar syntactic coding expansion, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds NOTHAS/TIME dialog markers and a multi-page reading panel, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies all _shared/ infrastructure, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships round #57, **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds cost optimization and dead man's switch, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 73, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** confirms round 60.

## wow_constructed_languages: Round 19 — Kalimag, Taur-ahe, Nerglish investigations; Shath'Yar coding expansion

One commit (1034 insertions, 11 deletions, 11 files):

### Kalimag

- +5 phonological patterns: apostrophe parallels Shath'Yar, /θ/ prevalence, Ignan vs Aquan vowels, gemination, rank-correlated name length
- +5 investigations: ma pronoun, krin copula, -os/-on/-an suffixes, dialect split, zoln conjunction

### Taur-ahe

- +7 phonological patterns: CV/CVC structure, apostrophe compounding, /h/ from /j/, open syllable preference, /ʃ/ prominence, disyllabic compound optimum, reduplicated -sha/-she
- +4 investigations: An- prefix, Ish- morpheme, -ahe suffix, -mani morpheme

### Nerglish

- +6 phonological patterns: murloc syllabic consonants, jinyu open syllables, -shi suffix, consonant expansion, ankoan shortening, kobyss loss
- +3 investigations: murloc→jinyu expansion, -shi suffix, Sele'na Zandali contact

### Shath'Yar

- Expand syntactic coding from 19 to 40+ codable phrases
- Add Extended Syntactic Coding section: S-Aux-V-O with wgah, S-Aux-Neg-V, S-Copula-Pred, V-imperative, Possessor-Possessed
- Upgrade SVO confidence from Moderate-High to High

### Elven comparative

- Integrate -ah derivational suffix analysis from Darnassian Investigation 14 into Correspondence 7 (productivity test, semantic consistency, Nazja evidence)

---

## open-divine-divinity-rust-bevy: Reading panel, NOTHAS/TIME markers, global sprite mapping

One commit (661 insertions, 148 deletions, 5 files):

- **Multi-page reading panel**: Book and Journal objects now open a dedicated reading panel instead of a dialog tree; long text is paginated at sentence boundaries (~400 chars/page); Arrow Left/Right or Enter/Backspace for navigation; page indicator shows "Page N/M"; ESC to close
- **NOTHAS/TIME dialog markers**: new `NOTHAS` (checks player does NOT have an item) and `TIME` (time-of-day condition) dialog markers added to the marker validation system
- **Global ID sprite mapping**: `ImagelistRange` table computes cumulative-sum base offsets for CPacked imagelists, enabling `overlay_tile_id` and `animation_index` from world data to resolve to specific sprite entries via `overlay_{global_id}` and `obj_{global_id}` keys

---

## mcp-russia: _shared/ infrastructure russification

One commit (383 insertions, 287 deletions, 22 files):

- **_shared/formatting.py**: value→znacheniye, headers→zagolovki, decimals→desyatichnykh, sign→znak, abs_value→abs_znacheniye, integer_part→tselaya_chast, decimal_part→drobnaya_chast
- **_shared/validators.py**: value→stroka, digits→tsifry, weights→vesa, remainder→ostatok, total→summa, check→kontrol
- **_shared/discovery.py**: params→parametry, properties→svoystva, meta→metadannye, server→server_fn, api_key→klyuch_api, client→klient, system_prompt→sistemnyy_prompt
- **_shared/planner.py**: params→parametry_str, api_key→klyuch_api, client→klient, system_prompt→sistemnyy_prompt
- **_shared/cache.py**: ttl→vremya_zhizni, expires_at→istekaet_v, now→seychas
- **_shared/batch.py**: fn_name→imya_fn, key→klyuch
- **_shared/lifespan.py**: server→server_fn, client→klient
- **_shared/rate_limiter.py**: now→seychas, cutoff→porog
- **feature.py**: meta→metadannye, server→server_fn (ZaregistrirovannayaFunktsiya)
- **server.py**: name→imya, result→rezultat
- Docs sync: code examples updated with real Russian API names; diagrams script labels russified; cliff.toml and pyproject.toml comments in Russian

---

## My-RU-Coverage: Round #57

One commit (188 insertions, 141 deletions, 31 files):

| Loanword | Russian replacement |
|----------|-------------------|
| история | определяющие факторы |
| фондирование | привлечение средств |
| транзакционный | расчётный |
| волатильный | изменчивый |

41+ replacements across 25 reports; enrichment JSON and graph data refreshed.

---

## tg_summarizer: Cost optimization, NLP filter metric, dead man's switch

One commit (222 insertions, 14 deletions, 8 files):

- **Cost optimization**: reduce `COVERAGE_CHECK_MAX_INPUT_CHARS` default from 2000 to 500
- **NLP filter metric**: new `_emit_nlp_filter_metric()` emitting Accepted/Rejected/AdFiltered/ShortFiltered counts via EMF
- **Dead man's switch**: `DeadMansSwitchAlarm` (Invocations < 1 over 24h, TreatMissingData: breaching)
- **Dashboard widgets**: NLP Filter (Channel) and NLP Filter (Group) widgets added
- 15 new tests (total 497)

---

## ru-skill: Round 73 — documentation russification

One commit (398 insertions, 311 deletions, 35 files):

- эндпоинт→конечная точка, адаптер→модуль-посредник, валидатор→модуль проверки, парсинг→разбор, браузерный→в обозревателе, env→переменные окружения, CI→система непрерывной интеграции, CLI→интерфейс командной строки, user-agent→пользовательский агент, трек-номер→номер отслеживания, and ~30 other hybrid terms
- Replacements across docs/features/*.md, SKILL.md files, package READMEs, AGENTS.md
- ~125 historical TODO.md section replacements
- YAML keys deemed unsafe for russification; document regression tests expanded

---

## codex-console-english: Round 60

One commit (7 insertions, 1 file):

- Verified no non-English text remains; all 32 tests pass

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
