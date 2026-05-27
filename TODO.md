---
published: false
---

# TODO

Latest automation round: 2026-05-27 (tenth round)

## Completed in this round

- Created new AUTOWORK post: **"AUTOWORK - autowork gains observability, mcp-russia reaches 13 modules with full test coverage"** (dated 2026-05-27).
  - Covers **autowork** observability improvements: persisted Telegram sync summary (`State.last_telegram_sync`), `review --json` for machine-readable output, guaranteed env keys in `doctor`, shell template base commands (`$PROMPT`), drift remediation hints, and failure-path regression tests.
  - Covers **mcp-russia** milestone: 13 Russian modules with full test coverage (1,815 tests passing). New Roskomnadzor and Rospotrebnadzor modules, server meta-tools translated to Russian, FastMCP 3.x bug fixes.
  - Covers **codex-console-english** ASCII cleanup: zero-width spaces and Unicode arrow replaced with ASCII equivalents, 29 tests still passing.
- Verified the site builds cleanly with `bundle exec jekyll build`.

## Next actions

- Commit and push the new post to `master`.
- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer as well if more posts accumulate and subscription becomes a primary navigation path.
- Consider adding tags or categories only if the technical-note section grows enough that a two-part archive stops being sufficient.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs instead of skipping that step.
- Monitor for updates on Denis Gordeev's Telegram channel (t.me/nlp_party) for NLP and text processing news to feature in future posts.
- Watch for new commits on autowork, mcp-russia, codex-console-english, and My-RU-Coverage for follow-up posts.
- Explore potential post on aggression/cyberbullying detection research (2016 work, highly cited at 38+ citations).
- Consider a deeper post on the autowork orchestrator's architecture if it gains significant new features.
- Consider a post on mcp-russia's real API integration progress once stubs are replaced with working endpoints.
