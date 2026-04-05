---
published: false
---

# TODO

Latest automation round: 2026-04-05

## Completed in this round

- Read `AUTOWORK_INSTRUCTIONS.md` and skipped creating a new post because an AUTOWORK article already exists for 2026-04-05.
- Retried the issue and PR step; `gh auth status` still reports an invalid GitHub token, so remote issue and PR inspection remains blocked locally.
- Split the archive into technical notes and `AUTOWORK` updates so repository-maintenance entries are easier to scan separately.
- Added a dedicated "Latest repository update" block on the homepage and About page to surface the newest AUTOWORK change without mixing it into profile links.
- Verified the site build with `bundle exec jekyll build` after the template updates.

## Next actions

- Refresh the CV file if a newer public version is available.
- Keep adding AUTOWORK posts only when there is a meaningful public update and not more than once per day.
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider adding tags or categories only if the technical-note section grows enough that a two-part archive stops being sufficient.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs instead of skipping that step.
