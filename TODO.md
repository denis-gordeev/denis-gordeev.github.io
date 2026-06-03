---
published: false
---

# TODO

Latest automation round: 2026-06-03 (nineteenth round)

## Completed in this round

- Reviewed all public repos for new activity since the eighteenth round's blog post (June 2, ~17:27 UTC).
- Created June 3 blog post covering: wow_constructed_languages (new repo, 17 conlangs with IPA and comparative linguistics), mcp-russia (Госдума/Закупки/КАД APIs, 7 real API modules), tg_summarizer (timeout and truncation hardening), ru-skill (continued russification on feat/mchs-storm-warnings), My-RU-Coverage (legacy term cleanup, MOEX tickers), codex-console-english (rounds 23–24), russia-md (upstream review).
- Updated TODO.md with current round status.

## Repo activity summary (post-blog 2026-06-02 to 2026-06-03)

### wow_constructed_languages (3 commits)

- **Initial commit** (14:56): Grammars and descriptions for 11 WoW constructed languages.
- **Expansion** (15:14): IPA transcriptions, comparative elven linguistics (Proto-Elven reconstruction), example sentences (non-canon), 3 new languages (Pandaren, Vulpera, Eredun/Demonic).
- **Further expansion** (18:05): IPA/HTML vocab for 7 more languages, Draenei/Eredun comparative, 3 more languages (Mogu, Sethrak, Nature/Druidic), expanded vocabularies with BfA/Legion/WoD content.

### mcp-russia (2 commits)

- **Госдума and Закупки APIs** (07:54): api.duma.gov.ru and zakupki.gov.ru with cross-module ФНС integration.
- **КАД API and russification** (17:46): kad.arbitr.ru court arbitration, redator module russified, documentation cleanup.

### ru-skill (4 commits on feat/mchs-storm-warnings)

- **English→Russian translation** (08:04): Boundary note, SKILL.md h1, package READMEs, frontmatter descriptions.
- **Legacy boundary copy russification** (12:11).
- **Transition copy and metadata alignment** (12:28).
- **Changeset summaries and SKILL.md frontmatter russification** (17:55): doc-regression tests expanded.

### tg_summarizer (2 commits on autowork/2026-04-08-lambda-hardening)

- **Cache invalidation fixes, code dedup** (08:05): text_hash→utils, defensive SummaryInfo, cost optimization.
- **Timeout and truncation hardening** (18:03): OpenAI timeout, NLP truncation, fetch limit, Telegram connect timeout.

### My-RU-Coverage (2 commits)

- **Anglicism annotations** (17:13, June 2): Russian explanations for 12 anglicisms, script russification.
- **Legacy term cleanup** (07:10, June 3): 27 TECH_TERMS, 13 MATERIAL_TERMS, WIKILINK_ALIASES fix, LOCAL_COMPANY_TICKERS, discover.py sector alignment.

### codex-console-english (2 commits)

- **Round 23** (17:20, June 2): all 29 tests pass.
- **Round 24** (07:21, June 3): no new non-English text found.

### russia-md (1 commit)

- **Upstream review** (12:17, June 2): no additional applicable fixes.

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026.
- Recent forwarded posts are from ecom.tech about Samokat "Вау-поиск" and FastML (courier partner internship story).

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, birdclef_2026, open-divine-divinity-rust-bevy, tg_summarizer, ru-skill, wow_constructed_languages for follow-up posts.
- Track birdclef_2026 embedding cache split approach to resolve the Kaggle timeout.
- Track mcp-russia's continued real API integration (7 of ~20 modules connected).
- Track ru-skill russification completion on feat/mchs-storm-warnings.
- Track wow_constructed_languages expansion (17 languages, IPA, comparative linguistics so far).
- Track My-RU-Coverage continued legacy term cleanup and russification.
