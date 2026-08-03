---
title: "AUTOWORK - Three repos August 3: mcp-russia MCP-registry validation and rosstat/gosduma client typing, My-RU-Coverage round 92 APC and dataframe russification, codex-console-english round 97 Chinese-English calque fixes"
date: 2026-08-03
layout: post
---

Three monitored repos land new commits since the previous round (July 29). **mcp-russia** adds MCP-registry example validation with 145-line test suite, and types the rosstat and gosduma clients with safe coercion helpers. **My-RU-Coverage** round 92 russifies APC→АПЦ, json_графа→строка_графа, and df_годовые/квартальные→таблица_годовые/квартальные. **codex-console-english** round 97 fixes 17 Chinese-English calques across 19 source and template files.

## mcp-russia: MCP-registry validation and client typing

### MCP-registry example validation

Adds `tests/test_documented_tools.py` (145 lines) that cross-references code examples in documentation against the actual FastMCP tool registry. Iterates all data and agent packages, discovers registered tools and their parameters, and asserts that every documented call matches a real tool with matching parameter names. Also archives the old TODO into `docs/TODO_ARCHIVE.md` (4634 lines) and updates example docs for gosudarstvennaya-politika, municipalnyy-kontrol, parlamentskiy-otchet, and zhurnalist-stati. 19 files changed.

### Rosstat client typing

Introduces `_stroka()` and `_chislo()` safe coercion helpers in `rosstat/client.py`, replacing raw `.get()` calls on external API responses. Ensures `period` fields always return `str`, numeric fields (`vrp`, `zarplata`, `dolya_vvp`) return `float | None`, and `edinitsa` defaults to empty string. Adds 75 new tests in `test_client.py`. 4 files changed.

### Gosduma client typing

Introduces `_stroka()`, `_tseloe()`, `_pervoe_znachenie()`, and `_spisok_iz_otveta()` helpers in `gosduma/client.py`. Replaces nested `.get()` chains with safe typed accessors for deputy, law, and vote fields. Adds 96 new tests in `test_client.py`. 4 files changed.

---

## My-RU-Coverage: Round 92 — APC and dataframe russification

Russifies financial code terminology: APC→АПЦ (Шнайдер Электрик), json_графа→строка_графа, df_годовые/квартальные→таблица_годовые/квартальные. Updates WIKILINKS.md, network graph data, and build/update scripts. 8 files changed with 147 insertions and 133 deletions.

---

## codex-console-english: Round 97 — Chinese-English calque fixes

Fixes 17 Chinese-English calques across Python backend and JavaScript frontend: "is normal"→natural, "Total Page"→page total, "is enabled"→active, and similar patterns in upload, email, outlook, and settings modules. 19 source/template files plus TODO.md updated. All 32 tests pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
