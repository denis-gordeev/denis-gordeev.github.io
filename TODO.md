---
published: false
---

# TODO

Latest automation round: 2026-06-01 (sixteenth round)

## Completed in this round

- Reviewed all public repos for new activity since the fifteenth round's blog post (May 30).
- Created 2026-06-01 blog post covering: mcp-russia docs/examples russification (2 commits), russia-md validator error limits + upstream SEO/contributor syncs (3 commits), My-RU-Coverage Anglicism annotations (1 commit), codex-console-english round 21 (1 commit).
- Updated TODO.md with current round status.

## Repo activity summary (2026-05-30 to 2026-06-01, post-previous-blog-post)

### mcp-russia (2 commits)
- **Brazilian tool IDs → Russian in docs/examples/** (510 changes): bacen→cbrf, ibge→rosstat, duma→gosduma, cik→cekrf, datajud→kad_arbitrazh, saude→minzdrav, transparencia→zakupki across four example personas. Fixed CI/CD workflows (removed non-existent src/mcp_brasil/ from mypy).
- **Russification of CONTRIBUTING.md, diagrams, docs** (298 changes): Portuguese code examples → Russian, generate_diagrams.py fully translated, docs navigation (Быстрый старт, Умные инструменты), fixed broken tool identifiers in examples, CHANGELOG cleanup.

### russia-md (3 commits)
- **Markdown validator ergonomics** (133 changes): `--markdown-error-limit` CLI flag, `SKILL_VALIDATOR_MAX_MARKDOWN_ERRORS` env var, errors grouped by source file before truncation, 3 new test cases.
- **Upstream SEO schema fixes** (84 changes): enhanced SEO.astro with structured data markup.
- **Contributor hardening + deploy** (66 changes): non-GitHub contributor support (static chips), profile URL validation, deploy workflow → ubuntu-latest.

### My-RU-Coverage (1 commit)
- **Anglicism annotations** (102 changes): Russian explanations at first mention for финтех/провайдеры/эквайринг/колокация/ритейл/девелопер/клиринг across 13 reports, utils.py typo fix.

### codex-console-english (1 commit)
- Round 21: translation scan complete, all 29 tests pass.

## Telegram channel (t.me/nlp_party)
- Recent posts are reposts from ecom.tech (Вау-поиск / Wow-search for Samokat) and FastML (Intern Courier Partner).
- No original posts by Denis Gordeev since April 27, 2026.

## Next actions

- Write the next blog post if meaningful new activity appears (once-per-day rule).
- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, birdclef_2026, open-divine-divinity-rust-bevy, tg_summarizer, ru-skill for follow-up posts.
- Consider a post on mcp-russia's real API integration progress once stubs are replaced with working endpoints.
- Consider a post on birdclef_2026 competition progress as the deadline approaches.
