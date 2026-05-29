---
published: false
---

# TODO

Latest automation round: 2026-05-29 (thirteenth round)

## Completed in this round

- Wrote 2026-05-29 blog post covering autowork per-project healing, mcp-russia second migration wave (18 modules, 1896 tests), My-RU-Coverage Russian-only pipeline, and codex-console-english rounds 16–17.
- Reviewed all public repos for new activity since 2026-05-28.
- Updated TODO.md with current round status.

## Repo activity summary (2026-05-28, post-previous-blog-post)

### autowork (3 commits)
- `run --self-heal` — regenerates drifted controller and managed wrappers before syncing projects.
- `telegram-sync --json --self-heal` — per-project healing visibility in JSON output, with `controller_healed`, `drifted_paths`, and `healed_paths` in `wrapper_contracts` payload.
- `history --until` — upper-bound timestamp filtering, complementing `--since` for range queries.
- Per-project granular healing/drift mappings (`per_project_healed`, `per_project_drifted`) in all JSON output surfaces.

### mcp-russia (2 commits)
- **GIBDD/MVD module** (ГИБДД/МВД): 12 tools, 3 resources, 2 prompts.
- **Minobrnauki module** (Минобрнауки): 12 tools, 3 resources, 2 prompts.
- `format_number_br` → `format_number_ru` migration across 90+ call sites.
- **Second migration wave**: `format_brl` → `format_rub`, `parse_brl_number` → `parse_rub_number`, Portuguese infrastructure names → Russian, server MCP tools renamed (`listar_features` → `spisok_funktsiy`, etc.), `McpBrasilError` → `McpRussiaError`.
- **Total modules now: 18**, 1,896 tests passing, ruff clean.

### My-RU-Coverage (2 commits)
- Removed legacy Taiwan scripts and batch workflow (−1,309 lines, +80 lines) — full Russian-only pipeline.
- Purged Chinese regex from `update_enrichment`, translated English remnants in scripts, deprecated legacy generators.

### codex-console-english (2 commits)
- Rounds 16 and 17 of English translation verification — no non-English text found, all 29 tests pass.

### russia-md (1 commit)
- Upstream review pass — checked for new fixes from taiwan-md upstream; none applicable.

## Telegram channel (t.me/nlp_party)
- Last post: April 27, 2026 (FastML "Intern Courier Partner").
- No new posts in May 2026.

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage for follow-up posts.
- Consider a post on the FastML "Intern Courier Partner" experiment from t.me/nlp_party (April 27 post) if relevant.
- Consider a post on mcp-russia's real API integration progress once stubs are replaced with working endpoints.
