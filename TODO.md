---
published: false
---

# TODO

Latest automation round: 2026-05-28 (eleventh round)

## Completed in this round

- Created new AUTOWORK post: **"AUTOWORK - autowork gains self-healing doctor and sync history, mcp-russia reaches 16 modules"** (dated 2026-05-28).
  - Covers **autowork** self-healing: `doctor --self-heal` regenerates drifted wrappers, `State.telegram_sync_history` ring buffer (last 10 summaries), per-project dispatch outcomes in `review`, collision-aware cron scheduling, root wrapper drift fix, 5 new regression tests.
  - Covers **mcp-russia** expansion to 16 modules: new FNS (Tax Service), Rosreestr (Registry/Cadastre), FSSP (Bailiff Service) modules; Portuguese-to-Russian function name migration across 7 existing modules (cbrf, gosduma, publikatsii, rosaudit, rosgidromet, rosstat, rosvodresursy).
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
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, and My-RU-Coverage for follow-up posts.
- Explore potential post on aggression/cyberbullying detection research (2016 work, highly cited at 38+ citations).
- Consider a post on mcp-russia's real API integration progress once stubs are replaced with working endpoints.
- Consider a post on the Portuguese-to-Russian migration pattern as a case study in codebase localization.
