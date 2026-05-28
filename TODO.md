---
published: false
---

# TODO

Latest automation round: 2026-05-28 (twelfth round)

## Completed in this round

- Verified the 2026-05-28 blog post was already committed and pushed.
- Reviewed all public repos for new activity since the last post.
- Identified significant new repo activity not yet covered in a blog post (see Next actions below).
- Updated TODO.md with current round status.

## New repo activity (2026-05-28, post-blog-post)

### autowork (3 additional commits)
- `run --self-heal` — regenerates drifted controller and managed wrappers before syncing projects (extends `doctor --self-heal` and `review --self-heal` to the run surface).
- `telegram-sync --json --self-heal` — now includes `controller_healed`, `drifted_paths`, and `healed_paths` in `wrapper_contracts` payload for per-project healing visibility.
- `history --until` — upper-bound timestamp filtering, complementing `--since` for range queries.
- `run --format json` with `--self-heal` reports `controller_healed` and `healed_paths`.

### mcp-russia (1 commit — 58 files changed, +4,094 lines)
- **GIBDD/MVD module** (ГИБДД/МВД): 12 tools (fines, vehicle check, driver license, crash stats), 3 resources, 2 prompts.
- **Minobrnauki module** (Минобрнауки): 12 tools (universities, grants, rankings, PhD programs), 3 resources, 2 prompts.
- `format_number_br` → `format_number_ru` migration across entire project (90+ call sites, 52 test files updated).
- **Total modules now: 18** (was 16 at time of last blog post).
- All 1893 tests passing, ruff clean.

### codex-console-english (2 commits)
- Rounds 16 and 17 of English translation verification — no non-English text found, all 29 tests pass.

### russia-md (1 commit)
- Upstream review pass — checked for new fixes from taiwan-md upstream; none applicable.

## Telegram channel (t.me/nlp_party)
- Last post: April 27, 2026 (FastML "Intern Courier Partner" — ML model for courier load optimization at Samokat, dogfooding as courier).
- No new posts in May 2026.

## Next actions

- **Write a new AUTOWORK post** covering the additional autowork and mcp-russia updates (on 2026-05-29 or later):
  - autowork: `run --self-heal`, `telegram-sync --json --self-heal` per-project healing, `history --until`, `run --format json` with heal details.
  - mcp-russia: 18 modules (GIBDD + Minobrnauki), `format_number_br` → `format_number_ru` full migration.
- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer as well if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage for follow-up posts.
- Consider a post on the FastML "Intern Courier Partner" experiment from t.me/nlp_party (April 27 post) if relevant.
- Consider a post on mcp-russia's real API integration progress once stubs are replaced with working endpoints.
- Consider a post on the `format_number_br` → `format_number_ru` migration as a case study in codebase localization.
