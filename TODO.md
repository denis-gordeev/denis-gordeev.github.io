---
published: false
---

# TODO

Latest automation round: 2026-06-10 (twenty-sixth round)

## Completed in this round

- Scanned all monitored repos for new commits since the twenty-fifth round blog post.
- Identified new activity in wow_constructed_languages (3 commits: Eredun/Pandaren/Vulpera standard language files, kobyss research with Drust Stele catalog and Hallowfall place names, murloc/jinyu/ankoan/kobyss language family analysis — 1,596 lines added), tg_summarizer (1 commit: critical truncation bug fix UPDATE_SUMMARY_MAX_TOKENS 500→2000, indentation bug dropping NLP messages, cost optimization, 146 tests), birdclef_2026 (3 commits: experiments 048 extended soundscape training MIXED, 049 rank-averaging ensemble POSITIVE +0.087 AUC, 050 meta-augmented probes NEGATIVE — 2,857 lines added), ru-skill (1 commit: English comments/JSDoc/test descriptions russified across all target packages, 131 tests), open-divine-divinity-rust-bevy (1 commit: merchant trading, skill particle effects, enemy patrol/ranged AI — 1,016 lines added).
- Created AUTOWORK blog post for June 10 covering five repos/projects.
- Updated TODO.md with current round status and queued new activity for the next post.

## Repo activity summary (post-blog 2026-06-10, twenty-sixth round)

### wow_constructed_languages (3 new commits since twenty-fifth round)

- **Eredun, Pandaren, Vulpera standard language files** (June 9): Three languages previously had only index.html; now each has full vocabulary.md, grammar.md, description.md, and vocabulary.html. Cross-references updated. 532 lines added across 14 files.
- **Kobyss research, Drust Stele catalog, Hallowfall place names** (June 9): 25+ kobyss NPC names (all Common descriptors), ankoan descent lore; Drust Steles expanded from 4 to all 10; 9 Arathi personal names, 12+ place names; ethereal updates (Devouring Host, Dark Heart, Voidstorm). 733 lines added across 7 files.
- **Murloc/jinyu/ankoan/kobyss language family analysis** (June 9): Full evolutionary chain from Murloc (Nerglish) through Jinyu and Ankoan to Kobyss; 5 ankoan names, 30+ jinyu names, Nerglish phonotactic patterns, kobyss linguistic regression (3–5 Common words); 7 kobyss tribes, 5 chieftain names, cross-family phonological comparison table. 331 lines added across 4 files.

### tg_summarizer (1 new commit since twenty-fifth round)

- **Critical truncation fix, indentation bug, cost optimization** (June 9): UPDATE_SUMMARY_MAX_TOKENS 500→2000 (was silently truncating summaries); indentation bug dropped all but last NLP message per batch; intra-batch dedup moved before coverage checks; coverage context built once per call; ENABLE_SUMMARIES_DEDUPLICATION and ENABLE_SUMMARY_UPDATES env-configurable; extract_links strips trailing punctuation; length guard in update_existing_summary. 14 new tests (146 total, all passing).

### birdclef_2026 (3 new commits since twenty-fifth round)

- **048 Extended soundscape training (MIXED)** (June 9): MLP overfits, cosine prototypes fail (AUC 0.56), pseudo-labeling adds nothing. Tax blend still best at +0.073 AUC.
- **049 Rank-averaging ensemble (POSITIVE)** (June 9): +0.087 AUC beats tax_blend (+0.073) by +0.014. Best ensemble result so far.
- **050 Meta-augmented probes (NEGATIVE)** (June 9): Baseline/site/hour features hurt probes due to focal-soundscape distribution mismatch.
- 2,857 lines added across 5 files.

### ru-skill (1 new commit since twenty-fifth round)

- **English comments, JSDoc, test descriptions russified** (June 9): All target packages (yandex-rasp, osm-nearby, zoon-nearby, kinopoisk-search, stoloto-lotto, rpl-results, pravo-documents, kakao-bar-nearby, airkorea, mchs-storm-warnings). Doc-regression expanded. 131 tests pass, 1 skipped.

### open-divine-divinity-rust-bevy (1 new commit since twenty-fifth round)

- **Merchant trading, skill particle effects, enemy patrol/ranged AI** (June 9): Buy/sell items with gold; skill particle effects; Orc Archer ranged enemy; patrol AI. 1,016 lines added across game.rs and game/combat.rs. No remote configured — local-only development.

### mcp-russia, codex-console-english, My-RU-Coverage, repo-autowork

- No new commits since the twenty-fifth round.

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026. Recent channel activity consists of forwards from ecom.tech, Самокат, and FastML.

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Watch for new commits on autowork, mcp-russia, codex-console-english, russia-md, My-RU-Coverage, tg_summarizer, ru-skill, wow_constructed_languages, birdclef_2026 for follow-up posts.
- Track wow_constructed_languages continued morphological analysis — murloc language family now fully documented; watch for further language additions.
- Track mcp-russia continued expansion — now 22 active Russian modules with real API connections.
- Track ru-skill russification — comments/JSDoc now russified across all target packages; watch for remaining surfaces.
- Track My-RU-Coverage continued russification and abbreviation expansion.
- Track tg_summarizer continued pipeline improvements — truncation fix deployed; watch for further bug fixes.
- Track birdclef_2026 — rank-averaging ensemble at +0.087 AUC is current best; watch for new experiments.
- Track open-divine-divinity-rust-bevy local development — merchant trading and ranged AI in progress.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
