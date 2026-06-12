---
published: false
---

# TODO

Latest automation round: 2026-06-12 (thirtieth round)

## Completed in this round

- Scanned all 9 monitored repos for new commits after the 2026-06-11 twenty-ninth round — activity found in 6 of 9 repos.
- Created new AUTOWORK blog post for 2026-06-12 covering: wow_constructed_languages (Hara'ni -ka suffix deep analysis, -neia/-leia/-iea feminine decomposition, long /uː/ confirmed, corpus expanded to ~16 personal names / ~14 place names / ~11 cultural names), mcp-russia (ВРП industry structure by ОКВЭД, investments by activity type, 9,019 insertions), tg_summarizer (CloudWatch EMF latency metrics, anti-repetition prompts, config hardening, RESTORE_TIMEOUT_SEC), open-divine-divinity-rust-bevy (mount/fast travel, trap dungeon rooms, rune fusion — 47,324 insertions), ru-skill (~90 JS + 19 Python test descriptions russified, API→API-справочник), codex-console-english (webui auth redirect test coverage).
- Updated TODO.md with current round status.

## Repo activity summary (2026-06-12, thirtieth round)

Activity in 6 repositories since the twenty-ninth round.

### wow_constructed_languages

- 1 commit, 4,655 insertions, 21 deletions across 8 files
- **-ka suffix deepened**: three interpretations evaluated (hunter, entity/personification, severed/ritually bonded); broad agentive/personification preferred
- **-neia/-leia/-iea analysis**: shown to be three name stems + single *-a* feminine suffix, not three distinct suffixes
- **Long /uː/ confirmed**: *Fuunid* and *Ruutani* provide two independent attestations
- **Ruutani spelling resolved**: Wikipedia consistently uses "ruutani" (lowercase); confidence upgraded to Low–Moderate
- **Corpus expanded**: ~16 personal names, ~14 place names, ~11 cultural/faction names, 3 Midnight-era terms

### mcp-russia

- 1 commit, 9,019 insertions, 23 deletions across 16 files
- **Отраслевая структура ВРП**: new tool providing GRP breakdown by ОКВЭД sections
- **Инвестиции по видам деятельности**: new tool for investment in fixed capital by activity type
- 107 new test lines for Rosstat tools
- Documentation cleanup (Portuguese fixtures removed, guides updated)

### tg_summarizer

- 1 commit, 292 insertions, 27 deletions across 12 files
- **CloudWatch EMF latency metrics**: `_emit_openai_latency` emits Embedded Metric Format JSON on every OpenAI call
- **Anti-repetition prompts** updated
- **RESTORE_TIMEOUT_SEC** configurable (default 30s, rejects zero)
- 25 new tests (total 196)

### open-divine-divinity-rust-bevy

- 1 commit, 47,324 insertions, 92 deletions across 4 files
- **Mount/fast travel**: Horse (1.6x), War Wolf (1.4x), outdoor-only; fast travel to discovered areas
- **Trap dungeon rooms**: Poison Gas, Collapsing Floor, Timed Escape
- **Rune fusion**: 5 composite rune recipes (e.g., Might+Fortitude→Titan, Arcana+Insight→Archmage)

### ru-skill

- 1 commit, 254 insertions, 179 deletions across 11 files
- ~90 JS test descriptions and 19 Python test descriptions russified
- `## API` → `## API-справочник` section headers
- doc-regression expanded for English test descriptions and API headers

### codex-console-english

- 1 commit, 60 insertions, 3 deletions across 4 files
- WebUI auth redirect test coverage expanded (42 new test lines)

### birdclef_2026

- 1 commit (TODO.md update only, no code changes)

### My-RU-Coverage

- No new commits since twenty-ninth round

### repo-autowork

- 1 commit (dry-run read-only sync_projects)

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026. Recent channel activity consists of forwards from ecom.tech, Самокат, and FastML.

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, tg_summarizer, ru-skill, wow_constructed_languages, birdclef_2026 for follow-up posts.
- Track wow_constructed_languages — Hara'ni morphological analysis deepening; watch for further confirmed etymologies and Midnight expansion data.
- Track mcp-russia — ВРП by ОКВЭД and investment tools now available; watch for new data sources.
- Track ru-skill — test russification continues; watch for remaining English surfaces.
- Track My-RU-Coverage — Round #31 russification; watch for further tech term explanations and wiki-link cleanup.
- Track tg_summarizer — EMF metrics and anti-repetition deployed; watch for further cost/reliability improvements.
- Track birdclef_2026 — competition closed; future ideas 060-063 queued for next BirdCLEF iteration.
- Track open-divine-divinity-rust-bevy — mounts, traps, rune fusion now in; watch for further gameplay systems.
- Track codex-console-english — auth redirect coverage expanded; watch for further webui improvements.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Next round should re-scan all repos for any commits after 2026-06-12.
