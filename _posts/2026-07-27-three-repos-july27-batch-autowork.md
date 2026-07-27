---
title: "AUTOWORK - Three repos July 27: wow rounds 92–94 CSS normalization and HTML-MD sync across 60 files, mcp-russia docs adaptation phrasing and example fixes, codex-console round 94 calque fix"
date: 2026-07-27
layout: post
---

Three monitored repos land new commits since the previous round. **wow_constructed_languages** completes rounds 92–94: CSS theme normalization for kalimag and nerglish, h3 color correction (#388e3c→#2e7d32) across 60 HTML files, and HTML-MD sync fixes spanning thalassian, pandaren, vrykul, sethrak, drust, dwarven, common, and vulpera. **mcp-russia** eliminates "adaptation" phrasing from documentation, fixes nonexistent tools and parameters in examples, and updates CONTRIBUTING.md. **codex-console-english** round 94 fixes the calque "Check topic" → "Check subject" in base.py.

## wow_constructed_languages: Rounds 92–94 — CSS normalization, h3 color fix across 60 files, HTML-MD sync (multiple insertions, 60+ files)

### Round 92 — CSS theme normalization (kalimag, nerglish), HTML-MD sync (common, vulpera, nerglish)

Normalizes CSS theme styling for kalimag and nerglish directories. Fixes HTML-MD sync gaps in common vocabulary, vulpera annotations, and nerglish missing content.

### Round 93 — CSS h3 color normalization across 60 HTML files, HTML-MD sync (sethrak, drust, dwarven)

Corrects h3 heading color from #388e3c to #2e7d32 across all 60 HTML vocabulary files for visual consistency. Fixes HTML-MD sync gaps in sethrak (dark theme, invisible headers), drust (missing Inferred labels, legend color), and dwarven (missing clause).

### Round 94 — HTML-MD sync fixes (thalassian, pandaren, vrykul)

Fixes CSS class mismatches and spurious annotations in thalassian. Corrects stale counts and anchor fragments in pandaren. Resolves navigation fixes and spurious labels in vrykul.

---

## mcp-russia: Docs — eliminate "adaptation" phrasing, fix nonexistent tools/parameters in examples, update CONTRIBUTING.md

Removes residual "адаптация" (adaptation) phrasing from documentation, replacing with more appropriate Russian terminology. Corrects examples that referenced nonexistent tools and parameters — ensuring all documented examples are accurate and runnable. Updates CONTRIBUTING.md to reflect current project conventions.

---

## codex-console-english: Round 94 — fix calque "Check topic" → "Check subject"

Fixes the Chinese-English calque artifact "Check topic" → "Check subject" in base.py. All 32 tests continue to pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
