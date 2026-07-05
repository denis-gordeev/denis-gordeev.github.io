---
title: "AUTOWORK - RU-Coverage round 61: MOEX→Московская биржа wikilink merge, script variable russification, README anglicisms"
date: 2026-07-05
layout: post
---

One repository updated on July 5: **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships round 61 with the final MOEX→Московская биржа wikilink merge, ~35 script variable renames to Russian, and README anglicism cleanup.

## My-RU-Coverage: Round 61 — MOEX wikilink merge, script russification, README cleanup

One commit (256 insertions, 264 deletions, 25 files):

### Wikilinks: [[MOEX]] → [[Московская биржа]]

- 12 report files updated: `**Рынок:** [[MOEX]]` → `**Рынок:** [[Московская биржа]]` across GMKN, TATN, MOEX, PHOR, LKOH, MTSS, SBER, GAZP, SNGS, VTBR, HYDR, MGNT
- Wikilink count drops 312 → 311 (MOEX and Московская биржа merged; Московская биржа now 34 occurrences)
- `WIKILINK_ALIASES` in utils.py updated with MOEX → Московская биржа alias to prevent re-introduction

### Витрина → площадка

- CNRU report: «единая витрина для поиска и аналитики» → «единая площадка для поиска и аналитики»
- WIKILINK_ALIASES updated with витрина → площадка alias

### README anglicisms

- «automation rounds» → «раунды автоматизации»
- «Legacy-тайваньский» → «Исторический тайваньский»
- «legacy-темы» → «устаревшие темы»
- «Legacy-корпус» → «Исторический корпус»

### Script variable russification (~35 variables, 6 files)

| File | Renames |
|------|---------|
| **utils.py** | TECH_TERMS→ТЕХНОЛОГИЧЕСКИЕ_ТЕРМИНЫ, MATERIAL_TERMS→ТЕРМИНЫ_МАТЕРИАЛОВ, APPLICATION_TERMS→ТЕРМИНЫ_КОНЕЧНЫХ_РЫНКОВ, GEO_TERMS→ГЕОГРАФИЧЕСКИЕ_ТЕРМИНЫ, REGULATORY_TERMS→НОРМАТИВНЫЕ_ТЕРМИНЫ, CATEGORY_COLORS→ЦВЕТА_КАТЕГОРИЙ, CATEGORY_LABELS→МЕТКИ_КАТЕГОРИЙ, LOCAL_COMPANY_TICKERS→ТИКЕРЫ_РОССИЙСКИХ_КОМПАНИЙ |
| **build_wikilink_index.py** | technologies→технологии, materials→материалы, applications→применения, companies_local→компании_российские, companies_intl→компании_иностранные |
| **discover.py** | TECH_SECTORS→СЕКТОРЫ_ТЕХНОЛОГИЙ, MATERIALS_SECTORS→СЕКТОРЫ_МАТЕРИАЛОВ, ENERGY_SECTORS→ЭНЕРГЕТИЧЕСКИЕ_СЕКТОРЫ, CONSUMER_SECTORS→ПОТРЕБИТЕЛЬСКИЕ_СЕКТОРЫ, FINANCE_SECTORS→ФИНАНСОВЫЕ_СЕКТОРЫ, SMART_PROFILES→УМНЫЕ_ПРОФИЛИ, PROFILE_LABELS→МЕТКИ_ПРОФИЛЕЙ |
| **audit_ru_reports.py** | LEGACY_THEME_MARKERS→УСТАРЕВШИЕ_ТЕМАТИЧЕСКИЕ_МЕТКИ, industry_acronyms→отраслевые_аббревиатуры, generic_patterns→шаблоны_общих_сущностей, generic_wikilinks→общие_викилинки |
| **build_themes.py** | RU_THEME_TAGS→ТЕМЫ_RU, RU_PRIORITY_QUEUE→ОЧЕРЕДЬ_ПРИОРИТЕТА_RU, upstream→верхний_контур, midstream→ключевое_звено, downstream→конечный_спрос, other→связанные |
| **update_financials.py** | METRICS_KEYS→КЛЮЧИ_МЕТРИК, METRIC_LABELS→МЕТКИ_МЕТРИК |

### Artifact rebuild

- WIKILINKS.md: 311 unique wikilinks (MOEX merged into Московская биржа)
- network/: 38 nodes, 75 edges
- themes/: 29 themes
- All 13 scripts compile without errors
- 42/42 (100%) reports pass quality audit

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
