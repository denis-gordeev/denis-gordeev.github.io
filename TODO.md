---
published: false
---

# TODO

Latest automation round: 2026-06-11 (twenty-eighth round)

## Completed in this round

- Scanned all monitored repos for new commits since 2026-06-10 — significant activity found in 7 of 9 repos.
- Checked t.me/nlp_party for new original posts by Denis Gordeev — no new original posts since April 27, 2026 (only forwards from ecom.tech, Самокат, FastML).
- Created new AUTOWORK blog post covering: wow_constructed_languages (Hara'ni language, Midnight expansion, TWW data), birdclef_2026 (+0.1207 AUC 3-way rank-averaging new best), tg_summarizer (NLP pre-filter, combined coverage+match, cost optimization), mcp-russia (ЕМИСС universal tool, Rosstat expansion), open-divine-divinity-rust-bevy (housing, companions, enchanting, puzzle dungeons), My-RU-Coverage (sector cleanup, 37 grammar fixes), ru-skill (final English jargon russification).
- Updated TODO.md with current round status.

## Repo activity summary (post-blog 2026-06-11, twenty-eighth round)

Major activity across 7 repositories since the twenty-seventh round.

### wow_constructed_languages

- 4 commits, 19,594 insertions across 21 files
- New Hara'ni (Haranir) language section with full linguistic analysis
- Midnight expansion language data: Aln- root, Ruutani, Hash'ey, domanaar, Zandali -ey suffix
- Wikipedia-confirmed TWW Undermine/Ghosts of K'aresh/Legacy of Arathor data
- Haranir deepened: -ia feminine suffix, Haranir-nerubian loanwords, Greenspeaker/Thornspeaker parallel
- All 10 Drust Stele inscription texts recovered

### birdclef_2026

- 3 commits, 3,469 insertions
- New best: +0.1207 AUC with 3-way rank-averaging (052c) — +0.034 above previous best
- Per-taxon rank-averaging at +0.1024 AUC (051)
- 052 probe techniques and 054 multi-view probes: negative

### tg_summarizer

- 2 commits, 824 insertions, 171 tests (all passing)
- NLP keyword pre-filter saves 30-50% of LLM calls
- Combined coverage+match check (saves 1 LLM call per covered message)
- Config validation, error handling, stale summary fix, cost optimization
- Lambda hardening: deadline propagation, message limits

### mcp-russia

- 2 commits, 765 insertions
- Universal indikator_dannye tool (ЕМИСС API)
- Rosstat expansion: ВРП, зарплата, региональные сравнения
- format_rub fix, API token unification, Portuguese fixture cleanup

### open-divine-divinity-rust-bevy

- 2 commits, 4,068 insertions
- Player housing, merchant restocking, skill tree, friendly NPC crossfire
- Companion system, puzzle dungeons, enchanting system, minimap markers

### My-RU-Coverage

- 2 commits, 80 files modified (988 insertions, 553 deletions)
- Eliminated "Не определено" sector (ASTR→Технологии, CNRU→Недвижимость)
- 37 grammar errors fixed in 18 reports
- 318+ generic wiki-links converted to plain text
- SECTOR_THEME_MAP for automatic theme generation

### ru-skill

- 1 commit
- Russified remaining English jargon (lookup, real-time, nearby, Sold out, etc.)
- JSDoc and source code comments translated, doc-regression expanded

### codex-console-english

- 3 commits (TODO.md updates only, no code changes)

### repo-autowork

- No new commits

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026. Recent channel activity consists of forwards from ecom.tech, Самокат, and FastML.

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, tg_summarizer, ru-skill, wow_constructed_languages, birdclef_2026 for follow-up posts.
- Track wow_constructed_languages — Hara'ni language now documented; watch for Midnight expansion additions and further Haranir morphological analysis.
- Track mcp-russia continued expansion — ЕМИСС universal tool now available; watch for new data sources.
- Track ru-skill russification — English jargon now fully russified; watch for remaining surfaces.
- Track My-RU-Coverage — "Не определено" sector eliminated; watch for further russification and grammar improvements.
- Track tg_summarizer — NLP pre-filter and combined checks deployed; watch for further cost/reliability improvements.
- Track birdclef_2026 — +0.1207 AUC is current best with 3-way rank-averaging; oracle gap only 0.0017; watch for new experiments.
- Track open-divine-divinity-rust-bevy — housing, companions, enchanting, puzzle dungeons now in; watch for further gameplay systems.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Next round should re-scan all repos for any commits after 2026-06-11.
