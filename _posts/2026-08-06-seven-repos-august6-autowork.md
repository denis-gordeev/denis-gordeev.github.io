---
title: "AUTOWORK - Seven repos update: wow Round 106, mcp-russia metadata, divine-divinity dedup, otclick v0.51 + GitLab CI, ru-skill rounds 117–118, ru-coverage rounds 96–97, codex-console rounds 101–102"
date: 2026-08-06
layout: post
---

Seven monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party could not be fetched (transport error). No new original posts by Denis Gordeev detected since April 27, 2026.

## wow_constructed_languages: Round 106 — gnomish, nerubian, qiraji, mogu

Round 106 audits four more directories for HTML-MD synchronization:

- **Gnomish**: Fixed bare `—` delimiters and IPA wrappers in grammar and vocabulary; corrected CSS class inconsistencies in vocabulary.html; synced vocabulary.md with HTML changes.
- **Nerubian**: Fixed 30+ bare `—` delimiters in vocabulary IPA columns; wrapped bare IPA references in description and grammar; synced vocabulary.md with HTML.
- **Qiraji**: Fixed bare `—` delimiters and IPA wrappers in description, grammar, and vocabulary; corrected CSS rules and nav separators.
- **Mogu**: Fixed bare `—` delimiters in vocabulary; corrected CSS classes in description and grammar; fixed factual errors in vocabulary entries.

19 files changed, 507 insertions, 483 deletions. Rounds 104–106 bring total to 10 directories audited since Round 103.

---

## mcp-russia: MCP metadata actualization, documentation checks

- Fixed outdated tool references: `cbrf_kursy_valyut` → `cbrf_tekushchie_kursy`, `gosduma_poluchit_deputatov` → `gosduma_spisok_deputatov`, `gosduma_raskhody_deputata` → `gosduma_info_deputata`, `rosstat_poluchit_indikator` → `rosstat_indikator_dannye`, `rosstat_poluchit_dannye_regiona` → `rosstat_informatsiya_o_regionye`.
- Fixed transliteration typos in features.md: `licenziy` → `litsenziy`.
- Expanded documentation testing: 4 new tests (bare names, source code, tool counts, tool names in features.md).
- Added machine-readable *(планируемый)* marker for unimplemented tools.
- Added `operatsii_trebuyut_avtorizatsii` field to MetaFunktsii; annotated Gosduma and Zakupki operations requiring authorized API.
- Added `generate_tool_reference.py` script for generating reference from registry.
- mypy: 0 errors, 784 tests pass.

---

## open-divine-divinity-rust-bevy: deduplicate handle_save_load, extract helpers

- Deduplicated `handle_save_load` by extracting `handle_skill_hotkeys` and `spawn_interactive_objects` helper functions.
- Added 27 unit tests (1216 → 1243).

---

## otclick: v0.51.0, GitLab CI, shellcheck fixes

- **v0.51.0**: Fixed `_late_limit` — cached `real_limiter.limit()` closure to prevent unbounded growth of slowapi `_route_limits` and `__marked_for_limiting` dicts. Trimmed Docker image with conditional COPY of alembic/alembic.ini/workspace.yaml via `INCLUDE_ALEMBIC` and `INCLUDE_WORKSPACE` build args. 2 new tests for `_late_limit` cache behavior.
- **GitLab CI**: Added full pipeline (lint/test/build).
- **Fixes**: Removed redundant `cd` in CI jobs, added shellcheck shell directive to `common.sh`.
- Verified completed TODO items, added round summary.

---

## ru-skill: Rounds 117–118

- **Round 117**: Eliminated "API" as standalone noun in interface documentation — replaced *Overpass API*, *ISS API*, *Wildberries API*, *Ozon Seller API*, *2GIS Catalog API*, *Яндекс.Карты Geosearch/Places API*, *Travel API*, *Kakao API* with «программный интерфейс ...» across all interface docs, source code, and tests. 18 files, ~30 occurrences.
- **Round 118**: Eliminated legacy-compatible proxy and fine-dust endpoint references in `secrets.env.example` and `check-setup.sh`; expanded documentation regression.

---

## My-RU-Coverage: Russification rounds 96–97

- **Round 96**: Fixed grammatical cases in wikilinks — `[[Московская биржа]]` → `[[Московская биржа|Московской бирже]]` (17 reports), `[[Краснодар]]` → `[[Краснодар|Краснодаре]]` (proposed case); resolved ambiguity `[[Виза]]` → `[[Visa]]` (VTBR); normalized `[[Хьюлетт Паккард Энтерпрайз]]` → `[[HPE]]` (DATA); replaced `[[госкомпании]]` with "государственные компании" per rule 1 in CLAUDE.md.
- **Round 97**: Renamed skill-files to Russian names, translated English comments in utils.py.

---

## codex-console-english: Rounds 101–102

- **Round 101**: Fixed ~19 Chinese-English calques — *Check if it is* → *Skip/Detect*, *Make sure* → *Ensure*, *Get the* → *Return*, *at the same time* → *concurrently*. All 32 tests pass.
- **Round 102**: Fixed 4 more Chinese-English calques — *Get the* → *Retrieve/Determine/Collect*, *is enabled* → *is configured*. All 32 tests pass.
