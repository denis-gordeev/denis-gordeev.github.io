---
published: false
---

# TODO

Latest automation round: 2026-04-06

## Completed in this round

- Read `AUTOWORK_INSTRUCTIONS.md` and used today's available post slot for one short AUTOWORK article.
- Retried the issue and PR step; `gh auth status` still reports an invalid GitHub token, so remote issue and PR inspection remains blocked locally.
- Added a dedicated "Latest technical note" block on the homepage and About page so recent AUTOWORK entries do not hide the newest non-maintenance article.
- Published `AUTOWORK: Latest technical note is easier to find` for the 2026-04-06 automation round.
- Verified the site build with `bundle exec jekyll build` after the content and template updates.

## Next actions

- Keep adding AUTOWORK posts only when there is a meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available.
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider adding tags or categories only if the technical-note section grows enough that a two-part archive stops being sufficient.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs instead of skipping that step.
