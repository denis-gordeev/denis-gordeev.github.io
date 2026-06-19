---
published: false
---

# TODO

Latest automation round: 2026-06-20 (forty-second round)

## Completed in this round

- Scanned all 9 monitored repos for new commits after 2026-06-19 20:00 UTC (forty-first round).
- **wow_constructed_languages**: 3 new commits — patch 12.1.0 Curse of Ula'tek data, 30+ confirmed Zandali primer words, first confirmed native Zandali sentences, verb morphology (ablaut/suffix/syntax), deepened analysis with 60+ wiki proper nouns, MD/HTML sync fixes.
- **mcp-russia**: 1 new commit — deepest code-level russification pass: ~67 Pydantic schema fields, ~1915 constants.py keys, ~60+ function parameters replaced across 93 files.
- **My-RU-Coverage**: 2 new commits — round #43 (дата-центр→ЦОД, инжиниринг→инженерно-технический, трейдеры→торговые компании, etc.) + логистика elimination (48 occurrences, 20 reports).
- **codex-console-english**: 2 new commits — ~100 Chinese calques fixed (modal box→modal, fill in→enter, etc.) + last Chinese characters removed.
- **ru-skill**: 1 new commit — scope→область действия, Endpoint→Эндпоинт, server-to-server→межсерверной, Legacy-совместимый→обратно совместимый, etc.
- **tg_summarizer**: 1 new commit — circuit breaker observability in Lambda response, prompt anti-verbosity, temperature sync fix, gpt-4.1-mini cost table.
- **open-divine-divinity-rust-bevy**: 1 new commit — real game asset loading: CMP archive parser, CPacked sprite index, DDS textures, 3-tier sound loading, 17 new tests.
- **birdclef_2026**: No new commits since fortieth round.
- Created AUTOWORK blog post for 2026-06-20 covering all 7 updated repos.
- GitHub API unreachable (auth token invalid); used local clones for commit scanning.
- Telegram channel t.me/nlp_party unreachable from current network; no new posts confirmed.
- Updated TODO.md with current round status.

## Repo activity summary (2026-06-20, forty-second round)

- **wow_constructed_languages**: 3 new commits (1374 insertions, 20 files) — patch 12.1.0 Curse of Ula'tek data with official IPA for Ula'tek; 30+ confirmed Zandali primer words from Moldy Diary/Hastily-Scribbled Note; first confirmed native Zandali sentences (Tokobo'ne na Amani'Zar, Doba quzhu ta tawbo, Untoh de alanke tono); verb morphology with singular/plural ablaut and person suffixes (-den/-ne/-nekan); Akil'='Eagle' prefix confirmed; 8 new NPCs; expanded pronoun system; deepened analysis with Kith'ix Aqir transmission, writing system, 60+ wiki proper nouns; MD/HTML sync fixes for nature/pandaren/vulpera/haranir.
- **mcp-russia**: 1 new commit (13417 insertions, 93 files) — deepest code-level russification: ~67 Pydantic schema field replacements, ~1915 constants.py key replacements, ~60+ function parameter replacements; full coordination across schemas/constants/client/tools/tests in all 22 modules.
- **My-RU-Coverage**: 2 new commits (447 insertions, 80 files) — round #43: дата-центр→ЦОД, инжиниринг→инженерно-технический, трейдеры→торговые компании, дистрибьюторы→оптовые поставщики, маркетмейкеры→поставщики ликвидности, дженерики→препараты-аналоги, софт→программное обеспечение, биллинг→расчётно-учётные системы, концерн→холдинг; abbreviations expanded (ТНП, ИБП, НПЗ, АЗС, ЖБИ, ГОК, САПР, СУБД); + логистика eliminated (48 occurrences, 20 reports, 42/42 pass audit).
- **codex-console-english**: 2 new commits (279 insertions, 38 files) — ~100 Chinese calques fixed (modal box→modal, fill in→enter, heartbeat detection→check, configuration→settings, exit IP→outgoing IP); last Chinese characters (对应的) removed from README.md and TODO.md.
- **ru-skill**: 1 new commit (236 insertions, 21 files) — scope→область действия, Endpoint→Эндпоинт, server-to-server→межсерверной, server-side→серверно отрендеренный, API proxy→прокси, booking-навыков→навыков бронирования, Legacy-совместимый→обратно совместимый, Legacy-резерв/файл/имя/формулировка→устаревш*, Local Telegram mirror→Локальный зеркальный канал; doc-regression expanded.
- **tg_summarizer**: 1 new commit (153 insertions, 7 files) — circuit breaker state in Lambda response (closed/open/half-open visible), prompt anti-verbosity, temperature sync fix, gpt-4.1-mini cost table, 110 new tests.
- **open-divine-divinity-rust-bevy**: 1 new commit (1060 insertions, 8 files) — real game asset loading: CMP Family A archive parser with XOR key deobfuscation, CPacked sprite index reader, DDS texture support, 3-tier sound loading (loose→CMP→procedural), asset debug panel, 17 new tests (591→608).
- **birdclef_2026**: No new commits since fortieth round.

## Telegram channel (t.me/nlp_party)

- No new original posts by Denis Gordeev since April 27, 2026 (unchanged; channel unreachable this round).

## Next actions

- Keep adding AUTOWORK posts only when there is meaningful public update and not more than once per day.
- Watch for new commits on all 9 monitored repos for follow-up posts.
- Track wow_constructed_languages — Zandali primer analysis is a major milestone with confirmed sentences and verb morphology; watch for further primer discoveries and Midnight expansion content.
- Track mcp-russia — deepest code-level russification complete (schemas + constants + function params); watch for remaining English identifiers or new modules.
- Track My-RU-Coverage — round #43 + логистика eliminated; watch for continued russification rounds.
- Track codex-console-english — all Chinese characters now removed; watch for remaining English quality issues.
- Track ru-skill — scope/server/Legacy terms russified; watch for continued russification and new skill modules.
- Track tg_summarizer — circuit breaker observability deployed; watch for further cost/reliability improvements.
- Track open-divine-divinity-rust-bevy — real game asset loading with CMP parser is a major milestone; watch for sprite rendering and further asset integration.
- Track birdclef_2026 — competition closed; future ideas queued for next BirdCLEF iteration.
- Refresh the CV file if a newer public version is available (current CV is from 2022).
- Add a lightweight projects or talks section if there is public material worth linking from the About page.
- Consider exposing the feed link in the header or footer if more posts accumulate.
- Consider adding tags or categories only if the archive grows enough.
- Authenticate `gh` locally so future rounds can inspect open GitHub issues and PRs.
- Monitor t.me/nlp_party for NLP and text processing news to feature in future posts.
- Next round should re-scan all repos for any commits after 2026-06-20 20:00 UTC.
