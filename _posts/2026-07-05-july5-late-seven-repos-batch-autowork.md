---
title: "AUTOWORK - WoW Investigations 11-12: genitive syntax and future marking, Divine Divinity area transitions, MCP-Russia rounds 65-66, RU-Coverage round 62, ru-skill rounds 77-78, tg_summarizer cost alarms, codex-console round 65"
date: 2026-07-05
layout: post
---

Seven repositories see new commits on July 5: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Investigations 11-12 with genitive order reanalysis and synthetic vs. analytic future distribution, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds area transition pre-loading and area-specific enemies, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies private attributes and mixed identifiers in rounds 65-66, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships round 62 with domain-specific terminology cleanup, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches rounds 77-78 with surface→interface and login→вход replacements, **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds prompt compaction and per-call-type cost alarms, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** fixes 67 Chinese-English translation artifacts and verifies zero CJK/Cyrillic in round 65.

## wow_constructed_languages: Investigations 11-12 — Genitive order reanalysis, synthetic vs. analytic future

Two commits (352 insertions, 11 deletions, 13 files):

### Investigation 11: Genitive Order Conditioned by Syntactic Position

Investigation 10's alienable/inalienable possession hypothesis is **refuted** by a comprehensive inventory of 15 genitive constructions:

- **Possessor-Possessed order** only appears in **direct object position** (3/3 = 100%)
- **Possessed-Possessor order** is default for all other positions (11/15 examples)
- **PP complements** always use Possessed-Possessor (6/6 = 100%)
- The **fssh minimal pair** is decisive: the same noun (*fssh* = "glory") with the same possessor (N'Zoth) appears in both orders, differentiated only by syntactic position (direct object vs. PP complement)
- Same speaker (Zon'ozz) uses both orders with the same possessor, ruling out dialectal or pragmatic explanations

| Syntactic Role | Possessor-Possessed | Possessed-Possessor |
|---------------|--------------------|--------------------|
| Direct object | 3 | 0 |
| PP complement | 0 | 6 |
| Subject | 1 | 3 |
| Predicate | 0 | 1 |

Confidence: **Moderate** for the syntactic position hypothesis.

### Investigation 12: *wgah* vs. *qi'* — Synthetic vs. Analytic Future

Four hypotheses tested for the two simple future markers:

1. **Register variation** — refuted: G'huun uses both *qi'* and *wgah* in comparable combat contexts
2. **Person conditioning** — refuted: both markers appear with 2nd and 3rd person subjects
3. **Syntactic position** (default prefix *qi'* vs. auxiliary *wgah* for complex constructions) — Low–Moderate confidence:
   - *qi'* is a bound prefix: subject always directly touches the verb (6/6 attestations)
   - *wgah* is a free auxiliary: stands between subject and verb
   - Two *wgah qam* ("will not") attestations vs. zero *qi'* + negation — suggests *wgah* is required when negation co-occurs with future tense
   - Typological parallel with French synthetic (*je chanterai*) vs. analytic (*je vais chanter*) future
4. **Unrelated homophonous markers** — possible but unparsimonious

Refined four-way future system:

| Marker | Type | Function |
|--------|------|----------|
| *qi'* | Prefix | Default future (synthetic) |
| *wgah* | Auxiliary | Future in complex constructions (analytic) |
| *agth* | Auxiliary | Obligative future ("shall") |
| *gag* | Auxiliary | Emphatic future ("WILL!") |

Investigation count updated: 10 → 12.

---

## open-divine-divinity-rust-bevy: Area transition pre-loading, path preview fix

Two commits (221 insertions, 18 deletions, 6 files):

### Path preview visualization on walkability revalidation (Jul 4)

- Stale `PathPreview` and `DestinationMarker` entities cleared and respawned when `revalidate_move_paths` recalculates the player's in-flight path
- Prevents stale visual preview after opening doors or changing walkability near the player
- 2 new tests (796 → 798 total)

### Area transition pre-loading, area-specific enemies, AreaTravel sound (Jul 5)

- Area transition pre-loading system: next area assets loaded during transition
- Area-specific enemy spawning: different enemy types per area definition
- `AreaTravel` sound event triggered on area transitions
- Audio playback expanded with new sound variant handling
- 801 total tests

---

## mcp-russia: Rounds 65-66 — Shared infrastructure and private attribute russification

Two commits (3148 insertions, 962 deletions, 79 files):

### Round 65: server_fn→server_funktsiya, element→zapis, context→kontekst

- **server_fn → server_funktsiya**: dataclass field, lifespan parameter, local variables (7 replacements in 4 files + tests)
- **element → zapis**: 19 `_razobrat_*` functions and ~32 loop variables (~350+ replacements)
- **context → kontekst**: 18+ prompt functions (~36 replacements)
- **_shared/ namespace**: namespace→prostranstvo_imen, queries→zaprosy, fn→funktsiya, func→funktsiya, meta→metadannye_ekz, client→klient, deps→zavisimosti, plan→plan_zaprosa, k→klyuch, v→znachenie
- **data/ module**: row→stroka_tablitsy, digits→tsifry_stroka, cls→klass_css, keys→klyuchi, default→znacheniye_po_umolchaniyu, m→valyuta, d→deputat
- Critical documentation fixes: ~70 wrong tool name replacements across 13 files, wrong vypolnit_paket JSON keys, module count 22→24
- All checks passed: ruff check, ruff format, 547 unit tests, mypy (183 errors — unchanged)

### Round 66: Private attributes, Cyrillic schema fields, mixed identifiers

- **_shared/ private attributes**: `_cache`→`_kesh`, `_enabled`→`_vklyucheno`, `_key`→`_klyuch`, `_default_ttl`→`_ttl_po_umolchaniyu`, `_max_entries`→`_maksimalno_zapisey`, `_cleanup_interval`→`_interval_ochistki`, etc.
- **Cyrillic schema fields**: `название`→`nazvanie`, `дата`→`data`, `номер`→`nomer`, `статус`→`status` in gosduma and publikatsii schemas
- **Mixed identifiers**: `rosgidromet_client`→`klient_rosgidromet`, `cekrf_client`→`klient_cekrf`
- **Test renames**: `_mock_cache`→`_maket_kesha`, `_mock_context`→`_maket_konteksta`, fixture and variable updates in test_feature.py, test_rate_limiter.py, test_tools.py
- 16 files, 216 insertions, 156 deletions

---

## My-RU-Coverage: Round 62 — Domain-specific terminology cleanup

One commit (185 insertions, 132 deletions, 32 files):

| Category | Change | Scope |
|----------|--------|-------|
| игрок → компания/участник | Market participant terminology | 12 reports |
| в теме/в темах → в сфере | Sector terminology | 6 reports |
| слой → уровень | Layer→level | 4 reports |
| сектора банков → банковского сектора | Grammatical correction | 3 occurrences |
| Фондирование → Привлечение средств | Financial terminology | VTBR |
| инвестиционная логика → определяющие факторы | Research terminology | ROSN, SNGS |
| люксовые → премиум-класса | Market segment | ALRS |
| пользовательских взаимодействий → обращений клиентов | Customer terminology | T |
| DataPro Latin alias removed | Wikilink cleanup | DATA |
| README/LEGACY.md/task.md | wikilinks→викилинки, batch→пакетные | Meta-docs |
| network/index.html | Маппинг→Сопоставление | Artifact |

- WIKILINK_ALIASES updated: +5 aliases
- Audit: 42/42 (100%); artifact rebuild without errors

---

## ru-skill: Rounds 77-78 — Surface→interface, login→вход, parser→разбор

Two commits (241 insertions, 95 deletions, 44 files):

### Round 77: Surface→interface in package README and SKILL.md

- Package README: поверхность→интерфейс (8 files, 10 occurrences), JSON-/HTML- hybrids (6 files, 8 occurrences), REST API expansion (2 files)
- SKILL.md: поверхность→интерфейс (delivery-tracking ×3), городо-ориентированный→по городу и категориям, не-200 статус→код ответа отличный от 200, жить в→находиться в
- AGENTS.md: Поверхности прокси→Интерфейсы прокси
- Test regressions updated for new terminology

### Round 78: User-facing documentation russification

- «поверхность» → «интерфейс» in user docs (booking-replacements, brand-inventory, sources, features)
- «логин» → «вход» across docs and SKILL.md files
- «парсинг/парсер» → «разбор/программа разбора» in feature docs
- 90 lines of new test regressions in skill-docs.test.js
- Roadmap expanded with new milestones

---

## tg_summarizer: Prompt compaction, per-call-type cost alarms

Two commits (426 insertions, 30 deletions, 9 files):

### Prompt compaction, NLP cost alarm (Jul 4)

- Prompt compaction: reduces token count in summarization prompts
- NLP cost alarm: CloudWatch alarm for NLP processing cost threshold
- Meta-artifacts expansion: additional metadata for observability
- 136 new test lines in test_digest_post_processing.py

### Per-call-type cost alarms (Jul 5)

- Per-call-type cost alarms: separate CloudWatch alarms for each call type (SUMMARIZE, UPDATE_SUMMARY, NLP)
- Meta-artifacts expansion: additional metadata captured
- 132 new test lines in test_digest_post_processing.py
- 60 new template.yaml lines for alarm definitions

---

## codex-console-english: Fix 67 translation artifacts, round 65 verification

Two commits (139 insertions, 75 deletions, 22 files + 7 insertions TODO-only):

### Fix 67 Chinese-English translation artifacts (Jul 5)

Stilted English → natural English across 22 files:

| Stilted form | Natural replacement |
|-------------|-------------------|
| Prioritize using | Prefer/Try first |
| call API to get | fetch a proxy URL |
| paging | pagination |
| listening | bind |
| API address | API URL |
| Operation | Actions (table headers) |
| Verify parameters | Validate input |
| takes precedence over | overrides |
| Query inbox | Check inbox |
| Task records | Tasks |
| Set tab page | Settings tabs |

### Round 65: Verified zero CJK/Cyrillic (Jul 5)

- Repository confirmed fully English — zero CJK or Cyrillic characters in source, templates, and JS
- All 32 tests pass

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
