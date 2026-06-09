---
published: false
---

# TODO

Latest automation round: 2026-06-09 (twenty-fifth round)

## Completed in this round

- Scanned all monitored repos for new commits since the twenty-fourth round blog post.
- Identified new activity in wow_constructed_languages (1 commit: nerubian scroll text analysis, -ar suffix, En- prefix, Earthen -oc/-roc, ethereal Arabic naming pattern — 487 lines added), mcp-russia (1 commit: all 27 Brazilian modules fully deleted with ~50k lines removed, 3 new Russian modules wired to real APIs, 601 tests pass), tg_summarizer (1 commit: critical bug fix for summary failure returning error string, token usage logging, 132 tests), ru-skill (1 commit: yandex-rasp and ktx_booking russification), codex-console-english (1 commit: Round 29 clean scan), open-divine-divinity-rust-bevy (1 commit: visual minimap, area dialogs, area quests, inventory swap/comparison — 1,073 lines added).
- Created AUTOWORK blog post for June 9 covering six repos/projects.
- Updated TODO.md with current round status and queued new activity for the next post.

## Repo activity summary (post-blog 2026-06-09, twenty-fifth round)

### wow_constructed_languages (1 new commit since twenty-fourth round)

- **Nerubian scroll text, -ar suffix, En- prefix, Earthen -oc/-roc, ethereal Arabic naming** (June 8): Full scroll text analysis (orthographic conventions, phonological evidence, morphological decomposition); -ar faction suffix investigation (5 attestations, Low–Moderate confidence); En- prefix (Very Low confidence); Earthen -oc/-roc (2 attestations, Very Low confidence); ethereal Arabic-inspired naming pattern (9/25 names, High confidence for deliberate Blizzard design). 487 lines added across 9 files.

### mcp-russia (1 new commit since twenty-fourth round)

- **Brazilian modules fully removed, Russian APIs wired** (June 8): All 27 Brazilian modules deleted (source + tests, ~50k lines removed); deprecated Brazilian aliases and validators removed; Portuguese 'resultado ok' → Russian 'rezultat ok'; 3 new Russian modules wired to real APIs with multi-source fallbacks (sovfed, kaznacheistvo, rosprirodnadzor). 601 tests pass, 1 skipped.

### tg_summarizer (1 new commit since twenty-fourth round)

- **Critical bug fix, token usage logging** (June 8): Fix critical bug where summarize_text/summarize_group_text returned error string posted to Telegram; now returns None. Coverage check .startswith('ДА'). OpenAI token usage logging. Elapsed seconds in Lambda response. 9 new tests (132 total, all passing).

### ru-skill (1 new commit since twenty-fourth round)

- **Yandex-rasp and ktx_booking russification** (June 8): Russified yandex-rasp fallback value and ktx_booking --seat-option help; expanded doc-regression tests.

### codex-console-english (1 new commit since twenty-fourth round)

- **Round 29 clean scan** (June 9): No new non-English text found, all 29 tests pass.

### open-divine-divinity-rust-bevy (1 new commit since twenty-fourth round)

- **Visual minimap, area dialogs, area quests, inventory swap/comparison** (June 8): Major feature update with 1,073 lines added across game.rs, dialog.rs, layout.rs, quests.rs. No remote configured — local-only development.

### My-RU-Coverage, russia-md, repo-autowork

- No new commits since the twenty-fourth round.

### birdclef_2026

- No new commits. Repo has no remote configured.

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026. Recent channel activity consists of forwards from ecom.tech, Самокат, and FastML.

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, tg_summarizer, ru-skill, wow_constructed_languages for follow-up posts.
- Track wow_constructed_languages continued morphological analysis — ethereal Arabic naming pattern implications for morpheme reliability.
- Track mcp-russia continued expansion — now 22 active Russian modules with real API connections.
- Track ru-skill russification completion.
- Track My-RU-Coverage continued russification and abbreviation expansion.
- Track tg_summarizer continued pipeline improvements — token usage logging now available for cost monitoring.
- Track open-divine-divinity-rust-bevy local development — minimap and quest system in progress.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Verify whether birdclef_2026 repo should be removed from monitoring (no remote, no new activity).
