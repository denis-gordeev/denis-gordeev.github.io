---
published: false
---

# TODO

Latest automation round: 2026-06-02 (seventeenth round)

## Completed in this round

- Reviewed all public repos for new activity since the sixteenth round's blog post (June 1, 20:28).
- Created 2026-06-02 blog post covering: birdclef_2026 pseudo-labeling & ensemble stacking + label fix (7 commits), open-divine-divinity-rust-bevy area transitions & audio playback (2 commits), tg_summarizer S3/history caching + async fix (2 commits), ru-skill heading normalization to Russian (4 commits), mcp-russia real API connections (1 commit), My-RU-Coverage застройщик + MOEX indexes (1 commit), codex-console-english round 22 (1 commit).
- Updated TODO.md with current round status.

## Repo activity summary (2026-06-01 post-blog to 2026-06-02)

### birdclef_2026 (7 commits)
- **026 pseudo-labeling v2 + 027 OOF analysis**: LOO fusion hurts on oof_base; simple averaging outperforms.
- **029 pseudo-labeling v3** (1,026 lines) + **030 ensemble stacking** (868 lines): per-sample R2 loss, multi-checkpoint stacking.
- **Soundscape label construction bug fix**: misaligned training targets in 029/030.
- **Focal padding bug fix + syntax fixes**: np.float32 typo, double parenthesis, unnecessary label mapping.
- **029 timed out on Kaggle** (9h): need split approach for embedding cache.

### open-divine-divinity-rust-bevy (2 commits)
- **Actual audio playback** (985 additions): new audio_playback.rs with procedural placeholder fallback.
- **Full area transitions** (815 additions): Catacombs, Castle Stormfist, Rivertown with zone definitions, spawn points, transition markers, save/load persistence.

### tg_summarizer (2 commits)
- **AsyncOpenAI event loop fix**: resolved Lambda deadlock from nested event loop calls.
- **S3 client caching, history caching, deadline during iteration, None-safe text** (303 changes): major performance and robustness improvements.
- **SSM client caching, message_id preservation, coverage check dedup** (225 changes).

### ru-skill (4 commits)
- **Canonical heading normalization** (381 changes across 48 files): all headings to consistent Russian scheme, Chinese character artifacts eliminated.
- **Setup and zoon skill normalization**: k-skill-setup/SKILL.md and packages/zoon-nearby/SKILL.md cleaned.
- **English headings → Russian**, last Korean doc fragments translated.
- **TODO governance tightened**.

### mcp-russia (1 commit)
- **Real API connections** (872 additions, 240 deletions): Open-Meteo weather API (rosgidromet), EGRUL legal entity registry (fns), Portuguese example filenames → Russian.

### My-RU-Coverage (1 commit)
- **девелопер → застройщик** in 4 reports, unified METRIC_LABELS dict, 7 MOEX sector indexes added.

### codex-console-english (1 commit)
- Round 22: translation scan complete, all 29 tests pass.

## Telegram channel (t.me/nlp_party)
- No new original posts by Denis Gordeev since April 27, 2026.

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
- Track birdclef_2026 embedding cache split approach to resolve the Kaggle timeout.
- Track mcp-russia's continued real API integration as more stubs get replaced.
- Track ru-skill heading normalization completion.
