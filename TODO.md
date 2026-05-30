---
published: false
---

# TODO

Latest automation round: 2026-05-30 (fifteenth round)

## Completed in this round

- Reviewed all public repos for new activity since the fourteenth round's blog post (May 29).
- Created 2026-05-30 blog post covering: birdclef_2026 group-temperature F1 gains + negative results, open-divine-divinity-rust-bevy RPG systems (dialog rewards, weather, status effects), tg_summarizer dedup/deadlock fixes, ru-skill legacy doc coverage, My-RU-Coverage continued localization, codex-console-english round 20.
- Verified Jekyll build succeeds.
- Updated TODO.md with current round status.

## Repo activity summary (2026-05-29 to 2026-05-30, post-previous-blog-post)

### birdclef_2026 (7 commits)
- **022 group-specific temperatures**: +0.062 MicroF1 over uniform T=5 (Aves T=10–20, Insecta/Amphibia T=1–2, Reptilia T=1). LOO CV confirms +0.060. Integrated into baseline.
- **020 zero-shot**: deprioritized — 28 missing species are non-Aves, Perch can't detect.
- **021 soundscape-only**: Perch adds zero signal for insect sonotypes.
- **023 postproc v3**: negative — grouped T ≈ T=4, no improvement.
- **024 insect spectral**: negative — worse than Perch.
- **009 temporal (GRU/TCN)**: negative — overfits on 59 files, AUC drops.
- **025 window aggregation**: max already optimal, no further gain.

### open-divine-divinity-rust-bevy (2 commits)
- Audio system (34 sounds, 6 categories), NPC day/night schedules, item comparison, area transitions, rest mechanic. 26 new tests (161 total).
- Dialog rewards (XP/gold/items), weather system (Rain/Snow/Fog with intensity), status effects (Poison/Freeze/Bleed/Weaken). 44 new tests (205 total).

### tg_summarizer (2 commits)
- Critical dedup bug fix for Russian responses, max_tokens 16K→4K, truncated update match context.
- Lambda deadlock fix (same-event-loop), SSM Parameter Store support, code dedup, Lambda 1024MB. 6 new tests (61 total).

### ru-skill (2 commits)
- Fixed legacy-as-operational-default copy, expanded doc-regression for legacy skills.
- Added workflow/content assertions for remaining legacy skills (kakaotalk-mac, daiso-product-search, delivery-tracking). Full coverage: all 13 target + all legacy skills.

### My-RU-Coverage (3 commits on May 29, 1 on May 30)
- May 29: English jargon replacement in reports, financial label localization (НИОКР, за 12 мес., Прогнозный P/E), N/A→Н/Д fix, FMCG→ТНП/CAD→САПР/IoT→интернет вещей, Russian glosses for SLA/ERP/EPC/POS/SaaS/IaaS/DDoS.
- May 30: викалинк→викилинк typo fix, Russian explanations for IPO/B2B/B2C/BaaS/DRaaS, replaced англоязычные термины (мерчанты→продавцы, селлеры→продавцы, фулфилмент→комплектация заказов, вендоры→производители, трейдинг→торговля, антифрод/комплаенс/скоринг), русификация комментариев и профилей в скриптах. 31 files changed.

### mcp-russia (3 commits on May 29)
- Complete `mcp_brasil` → `mcp_russia` package rename: all backward-compat shims removed.
- Documentation cleanup: зачистка устаревших ссылок на mcp_brasil и MCP_BRASIL_*.
- Docs: align mcp_russia and agenty references.

### repo-autowork / autowork (3 commits on May 29)
- `project-run --format json` — new `ProjectRunResult` dataclass with regression tests.
- `project-run --self-heal` — wrapper contract healing at individual project level, with regression tests.
- Fix controller-wrapper drift bug, normalize JSON output, simplify `sync_projects`.

### codex-console-english (3 commits)
- Rounds 18 and 19 on May 29, round 20 on May 30: translation scan complete, all 29 tests pass.

## Telegram channel (t.me/nlp_party)
- Recent posts are reposts from ecom.tech (Вау-поиск / Wow-search for Samokat) and FastML (Intern Courier Partner).
- No original posts by Denis Gordeev since April 27, 2026.

## Next actions

- Write a 2026-05-31 blog post if meaningful new activity appears (once-per-day rule).
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
