---
title: "AUTOWORK - Seven repos: Darnassian toponymy, Divine Divinity lore objects, MCP-Russia variable russification, RU-Coverage round #54, ru-skill round 72, tg_summarizer hardening, Codex-Console round 57"
date: 2026-07-02
layout: post
---

Catching up on July 1 commits across seven repositories: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** adds 32 Darnassian place names and a Thas morpheme investigation, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** gains dialog tree conditions and lore objects, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies ~76 local variables, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** delivers round #54 with loanword fixes and a P0 bugfix, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 72 with category-value and prose russification, **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds circuit-breaker refactor and meta-artifact expansion, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** replaces ~50 `configuration`→`settings` occurrences across 30 files.

## wow_constructed_languages: Darnassian toponymy, Thas morpheme, attestation upgrades

Two commits (397 insertions, 75 deletions, 24 files):

### Commit 1 — 32 Darnassian place names, Investigation 15

- Add 32 Darnassian untranslated place names from warcraft.wiki.gg (Bashal'Aran, Ordil'Aran, Shal'Aran, Tethris Aran, Satyrnaar, Quel'Dormir, Rut'theran, Thas'talah, Vashj'ir, etc.)
- New Investigation 15: **Thas** toponymic morpheme — Darnassian *Thas'talah* paired with Thalassian *Thas'alah / Thas'dorah*
- Expand Aran attestations 4→7, upgrade confidence to **Moderate-High**
- Expand *-naar* attestations 3→4, upgrade allomorphy to **Moderate**
- Upgrade Thalassian Thas/Thalas cognate from Low to **Low-Moderate**
- Add Darnassae alternative name and Blizzard grammar meta-statement

### Commit 2 — Broken links, Pandaren/Vulpera examples, HTML↔MD sync

- Fix 6 broken HTML links (drust titan-forged, nerubian alien-comparative, earthen nerglish, vrykul drust)
- Add missing anchor IDs to haranir/vocabulary.html
- Update README attestation levels: Kalimag Very Low→Low-Moderate, Taur-ahe Low→Low-Moderate, Orcish Moderate→Low-Moderate, Eredun Low→Low-Moderate
- Add Pandaren (6 sentences) and Vulpera (4 sentences) to example-sentences.html
- Sync Zandali, Darnassian, Thalassian, Common HTML files with MD counterparts

---

## open-divine-divinity-rust-bevy: Dialog tree conditions, lore objects

One commit (997 insertions, 20 deletions, 6 files):

- Enhanced `build_dialog_tree_from_text()` with conditional responses: `[QUEST:]`, `[QUEST_DONE:]`, `[HAS:]`, `[SKILL:]`, `[REP:]`, `[REWARD:]` — auto reputation effects from sentiment keywords, choice branching, `[XP:]`/`[GOLD:]` reward markers
- Inscription visual differentiation: stone slab color, z_layer 3.1, inscription_slab texture key, distinct minimap color
- New **Book**, **Journal**, **Statue** `InteractiveObjectKind` variants — 15 lore objects across Aleroth, Catacombs, Dark Forest, Black Ring Fortress, Dragon Rider's Lair; Books/Journals open dialog panels, Statues show combat log messages
- BookOpen sound, book/journal/statue texture keys, name-based detection in `from_world_partition()`
- 6 new tests (757 → 763 total)

---

## mcp-russia: ~76 local variable russifications across 30 files

One commit (436 insertions, 329 deletions, 29 files):

Remaining English local variables replaced with Russian equivalents across all data modules:

| Module | Key replacements |
|--------|-----------------|
| rosreestr | feature→объект_данных, rights→права_список, features→объекты_список, cost→стоимость_словарь, area_data→данные_площади |
| kad_arbitrazh | doc→документ, name→название, sides→стороны, raw→сыр_данные |
| gibdd | history→история, dtp→дтп_данные, restrict→ограничения_данные, driver→водитель_данные, categories→категории_ву |
| cekrf | attr_dict→словарь_атрибутов, tag_lower→тег_нижний, cell→ячейка, val→значение, turnout→явка |
| 9 tools.py | filter_text→текст_фильтра, region_text→текст_региона, filter_parts→части_фильтра |
| cbrf | prev_str→предыдущая_строка, name→название_валюты, rubles→рубли |
| rosstat | available→доступные, sorted_data→отсортированные_данные, val→значение |

---

## My-RU-Coverage: Round #54

One commit (188 insertions, 144 deletions, 23 files):

### Loanword replacements

| Loanword | Russian replacement |
|----------|-------------------|
| корпоративный | из числа предприятий |
| монетизировать | извлекать доход |
| Yandex Облако | Яндекс Облако |
| 3D | трёхмерного |
| NPK | АФК |
| стека | компонентов |

### P0 bugfix

`discover.py` filepath→путь, `_конец_ttm`→`_конец_скользящего_года` — synchronized with previously russified keys.

---

## ru-skill: Round 72

One commit (300 insertions, 192 deletions, 36 files):

- `docs/roadmap.md`: skill/package → навык/пакет, booking-research → исследование по заменам бронирования, update-check automation → автоматизация проверки обновлений
- `docs/install.md`: workspace-пакеты → пакеты рабочего пространства, npm-пакеты → пакеты npm, skill-сценарии → сценарии навыков
- All 28 SKILL.md: category values russified (finance→финансы, utility→утилиты, etc.)
- SKILL.md prose: env→переменные окружения, GitHub star→отметка звездой на GitHub, secrets file→файл секретов, raw HTML→исходный HTML, frontend→фронтенд, cookie→куки
- TODO.md: ~110 historical English→Russian hybrid replacements
- `scripts/skill-docs.test.js`: round 72 regression tests

---

## tg_summarizer: Circuit breaker refactor, meta-artifact expansion

One commit (201 insertions, 25 deletions, 8 files):

- Consolidate fallback append in `update_existing_summary` via `_append_link` helper
- Expand `strip_meta_artifacts`: added *в частности, между прочим, перейдём к, возвращаясь к, как показано*
- Refactor `call_openai` to use `get_circuit_breaker_state()` instead of inline threshold check
- Add 0-byte file size check in S3 download (removes empty files)
- Compact `UPDATE_SUMMARY_PROMPT` to save ~10 input tokens per update call
- 17 new tests (435 → 452 total)

---

## codex-console-english: Round 57 — configuration→settings

One commit (118 insertions, 83 deletions, 30 files):

Systematic replacement of `configuration` with `settings` across user-facing contexts and docstrings:

| Category | Before → After |
|----------|---------------|
| Module docstrings | "Configuration management" → "Settings management" |
| CRUD functions | "Create/Update/Delete … configuration" → "…settings" |
| HTTP client | "request configuration" → "request settings", "OpenAI specific default configuration" → "OpenAI-specific defaults" |
| Service base | "service configuration" → "service settings", "configuration options" → "settings options" |
| Web routes | "Email service configuration API routing" → "…settings API routing", "Filter sensitive configuration fields" → "…settings fields" |
| Templates | settings.html label update |

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
