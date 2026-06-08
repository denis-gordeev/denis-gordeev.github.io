---
published: false
---

# TODO

Latest automation round: 2026-06-08 (twenty-third round)

## Completed in this round

- Scanned all monitored repos for new commits since the twenty-second round blog post.
- Identified new activity in wow_constructed_languages (Qiraji, Ethereal/Broker — now 29 languages), mcp-russia (all 19/19 modules with real APIs — major milestone), tg_summarizer (intra-batch dedup, parallel NLP, 125 tests), ru-skill (comprehensive russification), My-RU-Coverage (acronym russification), and codex-console-english (casing fix).
- Created AUTOWORK blog post for June 8 covering all six repos.
- Updated TODO.md with current round status and queued new activity for the next post.

## Repo activity summary (post-blog 2026-06-08)

### wow_constructed_languages (2 new commits since twenty-second round)

- **Qiraji language, Ahn'qiraj Aqir substrate** (June 5): Added Qiraji as 26th language entry; Ahn- shared Aqir substrate analysis; -naxx/-nax geminate pattern; Elder Nadox; kobyss research.
- **Ethereal/Broker language, Undermine goblin names, Gnomish morpheme expansion** (June 5): Added Ethereal as 27th language entry; -esh/-aresh locative suffix; broker-ethereal dialect hypothesis; Undermine goblin names; -gaz/Gaz-, -wix/-ik, -gio morpheme analysis. Now **29 language folders**.

### mcp-russia (2 new commits since twenty-second round)

- **Минобрнауки, Роспотребнадзор, Роскомнадзор, Росстат real APIs** (June 5): Four more real government data sources; 16/19 modules.
- **rosvodresursy, minzdrav, rosaudit real APIs; Portuguese cleanup** (June 5): Final three modules connected; **all 19/19 modules now have real API integrations**; mixed-script fix; Portuguese cleanup. 1974 tests passed.

### tg_summarizer (2 new commits since twenty-second round)

- **Summary temperature, deterministic edits, code dedup** (June 5): Temperature 0.3, deterministic update edits, code cleanup.
- **Intra-batch dedup, parallel NLP, input truncation, cache fix** (June 5): SequenceMatcher dedup, NLP_CONCURRENT_CHECKS=5, SUMMARY_MAX_INPUT_CHARS=3000, cache fix for empty results. 125 tests (up from 112).

### ru-skill (4 new commits since twenty-second round)

- **Source code error messages, CHANGELOG headings, API response values russified** (June 5)
- **Repo-governance surfaces russified, mixed-language drift closed** (June 5)
- **GitHub Actions workflow russification, fix-changelog-headings.js** (June 5)
- **Shell helper statuses russified** (June 6)

### My-RU-Coverage (1 new commit since twenty-second round)

- **B2B/B2C/POS acronym expansion, BaaS/DRaaS wiki-links, typo fix** (June 5)

### codex-console-english (1 new commit since twenty-second round)

- **Database tab casing fix** (June 5)

### birdclef_2026, open-divine-divinity-rust-bevy

- Repos not found or private; remove from monitoring list or verify correct names.

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026. Recent channel activity consists of forwards from ecom.tech, Самокат, and FastML about Samokat's "Вау-поиск" feature and ML courier optimization.

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, tg_summarizer, ru-skill, wow_constructed_languages for follow-up posts.
- Track wow_constructed_languages expansion beyond 29 languages and continued morphological analysis.
- Track mcp-russia's continued maintenance and improvements now that all 19 modules are live.
- Track ru-skill russification completion.
- Track My-RU-Coverage continued CJK cleanup and russification.
- Track tg_summarizer continued pipeline improvements.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Verify whether birdclef_2026 and open-divine-divinity-rust-bevy repos still exist or should be removed from monitoring.
