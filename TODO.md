---
published: false
---

# TODO

Latest automation round: 2026-05-29 (fourteenth round)

## Completed in this round

- Reviewed all public repos for new activity since the thirteenth round's blog post.
- Found significant new May-29 commits across autowork, mcp-russia, My-RU-Coverage, codex-console-english, and russia-md — but a blog post already exists for 2026-05-29, so deferring to the next day per the once-per-day rule.
- Updated TODO.md with current round status.

## Repo activity summary (2026-05-29, post-previous-blog-post)

### autowork (3 commits)
- `project-run --format json` — new `ProjectRunResult` dataclass with regression tests, extending structured JSON output to the project-run subcommand.
- `project-run --self-heal` — wrapper contract healing now works at the individual project level, with regression tests.
- Fix controller-wrapper drift bug, normalize JSON output, simplify `sync_projects`.

### mcp-russia (2 commits)
- **Complete `mcp_brasil` → `mcp_russia` package rename**: all backward-compat shims (`mcp_brasil` aliases, deprecated imports) removed. This is the final step of the migration that began in earlier rounds — the `mcp_brasil` name no longer exists anywhere in the codebase.
- docs: align `mcp_russia` and `agenty` references.

### My-RU-Coverage (2 commits)
- **Financial label localization**: НИОКР, за 12 мес., Прогнозный P/E; bug fix N/A→Н/Д; FMCG→ТНП, CAD→САПР, IoT→интернет вещей; Russian glosses for SLA/ERP/EPC/POS/SaaS/IaaS/DDoS.
- **English jargon replacement in reports**: 30 English terms across 13 report files (proximity→у дома, private label→СТМ, e-grocery→продуктовый онлайн-ритейл, fashion→одежда и обувь, e-commerce→электронная коммерция, etc.). Unified N/A→Н/Д, Unknown→Не определено. Translated comments and section headers to Russian. 42/42 reports pass quality check.

### codex-console-english (2 commits)
- Rounds 18 and 19 of English translation verification — no non-English text found, all 29 tests pass.

### russia-md (1 commit)
- Sync selective upstream category mapping hardening.

## Telegram channel (t.me/nlp_party)
- Last post: April 27, 2026 (FastML "Intern Courier Partner").
- No new posts in May 2026.

## Next actions

- Write a 2026-05-30 blog post covering the May-29 commits (autowork project-run JSON + self-heal + drift fix, mcp-russia complete package rename, My-RU-Coverage financial label localization and jargon replacement, codex-console-english rounds 18–19, russia-md upstream sync).
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
