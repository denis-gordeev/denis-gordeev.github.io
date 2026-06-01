---
title: "AUTOWORK - mcp-russia docs & examples fully russified, russia-md validator gains error limits, My-RU-Coverage annotates Anglicisms"
date: 2026-06-01
layout: post
---

Two days since the last post, and the russification wave continues. **mcp-russia** has completed the translation of its documentation, examples, and diagram-generation scripts from Portuguese to Russian. **russia-md** received a substantial markdown validator upgrade with configurable error limits and upstream SEO/contributor improvements. **My-RU-Coverage** continues its meticulous Anglicism annotation across equity research reports. **codex-console-english** completed round 21 of its translation verification scan.

## mcp-russia: docs and examples fully russified

Two commits on May 30 and June 1 continued the Portuguese-to-Russian migration in **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)**.

### Brazilian tool IDs replaced in docs/examples/

The first commit (510 changes, 240+/270−) replaced all remaining Brazilian tool IDs in the four example personas:

| Example file | Brazilian IDs | Russian IDs |
|---|---|---|
| panorama-economico.md | `bacen_*`, `ibge_*` | `cbrf_*`, `rosstat_*` |
| economista.md | `bacen_*`, `ibge_*` | `cbrf_*`, `rosstat_*`, `zakupki_*` |
| cientista-politico.md | `duma_*`, `cik_*`, `datajud_*`, `saude_*`, `transparencia_*` | `gosduma_*`, `cekrf_*`, `kad_arbitrazh_*`, `minzdrav_*`, `zakupki_*` |
| jornalista-investigativo.md | `datajud_*`, `otkryte_dannye_*` | `kad_arbitrazh_*`, `rosstat_*`, `zakupki_*` |

CI/CD workflows (ci.yml, release.yml) were also fixed: the non-existent `src/mcp_brasil/` path was removed from mypy configuration.

### CONTRIBUTING.md, diagrams, and navigation translated

The second commit (298 changes, 170+/128−) completed the russification sweep:

- **CONTRIBUTING.md**: Portuguese code examples replaced with Russian ones (primer-feature, example.gov.ru, Subjekt, poisk_mestopolozheniy)
- **generate_diagrams.py**: all clusters, nodes, and labels translated to Russian; nodes updated from Brazilian to Russian modules
- **Docs navigation and headings**: Быстрый старт, Умные инструменты, Процесс участия
- **Example tool names**: fixed broken identifiers (splanirovat_zapros, vypolnit_paket), replaced Brazilian sources with Russian
- **CHANGELOG.md**: cleanup of remaining Portuguese terms

## russia-md: validator ergonomics and upstream sync

Three commits on May 30 and June 1 improved the **[russia-md](https://github.com/denis-gordeev/russia-md)** knowledge base.

### Configurable markdown error limits

The most substantial change (133 additions, 119+/14−) adds fine-grained control over markdown validation error reporting:

- **`--markdown-error-limit` CLI flag**: accepts a non-negative integer; `0` reports all errors, default remains 10
- **`SKILL_VALIDATOR_MAX_MARKDOWN_ERRORS` environment variable**: fallback when CLI flag is omitted
- **Grouped error output**: errors are now grouped by source file before truncation, so no single file monopolizes the limited error budget
- Three new test cases cover the flag at 0, 2, and the default

### Upstream SEO schema fixes

An 84-change commit (80+/4−) enhanced `SEO.astro` with structured data schema markup for better search engine indexing.

### Contributor hardening

A 66-change commit (55+/11−) improved the contributor attribution system:

- **Non-GitHub contributors**: contributor chips now support static (non-link) profiles for contributors without GitHub accounts
- **Profile URL validation**: only `github.com` hostnames are accepted as profile links, preventing arbitrary URL injection
- **Deploy workflow**: switched from `ubuntu-24.04-arm` to `ubuntu-latest` for broader runner compatibility

## My-RU-Coverage: Anglicism annotations

A June 1 commit (102 changes, 59+/43−) in **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** continued the systematic localization of equity research reports:

- **Anglicism annotations**: Russian explanations added at first mention for финтех, провайдеры, эквайринг, колокация, ритейл, девелопер, клиринг across 13 reports (Ozon, Cian, X5, Bazis, Magnit, AFK Sistema, MTS, Arenadata, BSPB, MOEX, Sber, T-Bank, VTB)
- **Typo fix** in utils.py
- Network graph data and index updated

## codex-console-english: round 21

Round 21 of the English translation verification scan on June 1 confirmed no non-English text remains. All 29 tests pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
