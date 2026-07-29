---
published: false
---

# TODO

Latest automation round: 2026-07-29 (eighty-eighth round)

## Completed in this round

- Scanned all 8 monitored repos for new commits since July 28; 5 repos have new meaningful commits (wow_constructed_languages 3, mcp-russia 2, open-divine-divinity-rust-bevy 1, ru-skill 1, otclick 3). codex-console-english, My-RU-Coverage, and birdclef_2026 have no new meaningful changes.
- Telegram channel t.me/nlp_party scanned; no new original posts by Denis Gordeev (recent activity is forwarded content from ecom.tech, Samokat, FastML — not attributable to Denis).
- Created blog post: 2026-07-29-five-repos-july29-batch-autowork.md covering wow rounds 96–98, divine-divinity layout extraction + 27 new tests, otclick v0.43–v0.45, mcp-russia element→zapis, ru-skill round 112.
- Updated TODO.md with current round status.

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content from ecom.tech, Samokat, FastML — not attributable to Denis).

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Watch for new commits on all 8 monitored repos for follow-up posts.
- Track wow_constructed_languages — Rounds 96–98 completed (July 29): HTML-MD sync across 10 directories (haranir, nerubian, mogu, qiraji, orcish, shath-yar, etc.); apostrophe normalization, asterisk conversions, IPA fixes, CSS additions, nav consolidation; watch for Round 99+.
- Track open-divine-divinity-rust-bevy — layout helper extraction (4958→3238 lines), InteractiveObjectDef/QuestTrigger/AreaTransition constructors, Plugin::build extraction (425→7 lines), WaveParams builder pattern, 27 new tests (1117→1144); watch for continued refactoring and test growth.
- Track mcp-russia — element→zapis russification (66 replacements), metadata refresh, migration-era phrasing cleanup; watch for continued russification and feature development.
- Track My-RU-Coverage — rounds 90–91 completed; no new commits this round; watch for continued russification rounds.
- Track ru-skill — round 112 completed (jargon revert elimination: эндпоинт, прокси, валидация, пагинация, ID); watch for continued audit rounds or new features.
- Track tg_summarizer — repo not found locally; watch for further cost/reliability improvements.
- Track codex-console-english — round 95 completed; no new commits this round; watch for any new features or artifacts.
- Track birdclef_2026 — competition closed; future ideas queued for next BirdCLEF iteration.
- Track otclick — v0.43.0→v0.45.0 (dead code removal, Depends() consolidation, httpx2 migration, Pydantic model extraction to models.py, coverage 98%); watch for further development.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
