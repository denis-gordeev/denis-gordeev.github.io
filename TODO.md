---
published: false
---

# TODO

Latest automation round: 2026-06-02 (eighteenth round)

## Completed in this round

- Reviewed all public repos for new activity since the seventeenth round's blog post (June 2, 07:27 UTC).
- No new blog post created: once-per-day rule (June 2 post already exists).
- Noted 5 repos with post-blog activity for the next round's post.
- Updated TODO.md with current round status.

## Repo activity summary (post-blog 2026-06-02 to now)

### wow_constructed_languages (new repo, 2 commits)

- **New repository** created at 2026-06-02T15:17:55Z (HTML language).
- **Initial commit** (14:56): Grammars and descriptions for 11 WoW constructed languages — Darnassian, Thalassian, Draenei, Orcish, Zandali, Taur-ahe, Dwarven, Shath'Yar, Kalimag, Shalassian, Gutterspeak. Each folder has vocabulary.md, grammar.md, description.md.
- **Expansion commit** (15:14): IPA transcriptions, comparative elven linguistics (Proto-Elven reconstruction, sound correspondences), example sentences (non-canon), 3 new languages (Pandaren, Vulpera, Eredun/Demonic). README and TODO updated.

### mcp-russia (1 commit)

- **Госдума and Закупки real APIs** (07:54): api.duma.gov.ru (депутаты, законопроекты, голосования) with DUMA_API_TOKEN, zakupki.gov.ru (поиск закупок, контракты, планы) with cross-module ФНС integration. 5 modules now have real APIs: ЦБ РФ, Росгидромет, ФНС, Госдума, Закупки. CHANGELOG Portuguese cleanup.

### ru-skill (3 commits on feat/mchs-storm-warnings)

- **English → Russian translation** (08:04): Boundary note → Граничное примечание in 31 files, 9 SKILL.md h1 headings, 10 package READMEs, 8 frontmatter descriptions. Heading normalization (Что умеет → Что делает навык, etc.). Doc-regression test updated for round 31.
- **Legacy boundary copy russification** (12:11): docs: russify legacy boundary copy surfaces.
- **Transition copy and metadata alignment** (12:28): docs: align transition copy and package metadata.

### tg_summarizer (1 commit on autowork/2026-04-08-lambda-hardening)

- **Cache invalidation bugs, code dedup** (08:05): text_hash → utils extraction, defensive SummaryInfo, cost optimization fixes.

### russia-md (1 commit)

- **Upstream review** (12:17): Review upstream/main at 7d2b0fef9 — no additional applicable fixes.

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026.
- Recent forwarded posts are from ecom.tech about Samokat "Вау-поиск" and FastML (courier partner internship story).

## Next actions

- **Write the June 3 blog post** covering: wow_constructed_languages (new repo), mcp-russia Госдума/Закупки APIs (5 real API modules), ru-skill English→Russian translation (3 commits), tg_summarizer cache fixes, russia-md upstream review.
- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, birdclef_2026, open-divine-divinity-rust-bevy, tg_summarizer, ru-skill, **wow_constructed_languages** for follow-up posts.
- Track birdclef_2026 embedding cache split approach to resolve the Kaggle timeout.
- Track mcp-russia's continued real API integration (5 of ~20 modules connected).
- Track ru-skill heading normalization completion (round 31 in progress on feat/mchs-storm-warnings).
- Track wow_constructed_languages expansion (14 languages, IPA, comparative linguistics so far).
