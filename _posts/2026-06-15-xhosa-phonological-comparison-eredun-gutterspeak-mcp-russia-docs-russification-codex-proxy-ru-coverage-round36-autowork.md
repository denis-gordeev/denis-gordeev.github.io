---
title: "AUTOWORK - WoW: Xhosa phonological comparison, Eredun/Gutterspeak example sentences; MCP-Russia: 64-file docs russification; codex-console: full English translation confirmed; My-RU-Coverage: round #36, new categories"
date: 2026-06-15
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository adds a detailed Xhosa phonological comparison with Hara'ni and Zandali, six Eredun and six Gutterspeak constructed example sentences, and cross-navigation across all comparative pages. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** completes a second large russification wave across 64 files (docs, tests, comments), fixing E501 lint and BM25 tests. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** reaches round 38: a full-codebase scan confirms complete English translation with all 32 tests passing. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** adds new classification categories (географический_объект, регулирование), eliminates 72+ generic wikilinks, and cleans up semiconductor terminology (rounds #35–#36).

## wow_constructed_languages: Xhosa comparison, Eredun/Gutterspeak sentences, link fixes

Three commits add 464 insertions, 99 deletions across 13+ files.

### Xhosa phonological comparison (Hara'ni vs Zandali)

A detailed Xhosa comparison is added to `haranir/grammar.md`: shared features (five-vowel system, CV syllable preference, apostrophe compounding, /a/ /i/ frequency, palato-alveolar series), divergent features (/h/ frequency, geminates, /θ/ /ʒ/ vs /f/ /v/ /z/), and Xhosa-specific features absent from WoW orthography (clicks, tone, ejectives, implosives, syllable-timed rhythm). An assessment table summarizes the parallels.

### Light Rutaani analysis

The "Light" prefix in Light Rutaani is identified as Common/English; no Hara'ni word for "light" is attested. The analysis is added to both `haranir/vocabulary.md` and `vocabulary.html`, with entries mirrored in `alien-comparative.html`.

### Eredun and Gutterspeak example sentences

Six Eredun and six Gutterspeak constructed example sentences are added to `example-sentences.html`, with the nav updated to include both new sections.

### Cross-navigation and link fixes

Eight broken `grammar.html` links fixed to `grammar.md` across HTML files; three broken anchor links repaired. A cross-navigation footer added to all five comparative/example HTML pages. Missing `h3` CSS added to earthen, shalassian, and shath-yar vocabulary pages. Tolvir vocabulary normalized to standard light theme/serif font.

## mcp-russia: 64-file docs/ russification, E501/BM25 fixes

One commit modifies 64 files (10,618 insertions, 609 deletions).

### Second russification wave

After the ~160-file docstring pass in the previous round, this commit russifies `docs/` documentation (125 replacements), test files (38 replacements), and inline comments (5 replacements). E501 line-length lint errors and BM25 test failures are corrected to keep the suite green.

## codex-console-english: full English translation confirmed (round 38)

Two commits add 198 insertions, 157 deletions.

### ~154 translation artifact fixes

Systematic fixes: `agent→proxy`, `self-deployed→self-hosted`, `mailing list→email list`, `interface→API`, plus broader English phrasing polish across the codebase.

### Round 38 scan: all clear

A full-codebase scan confirms no remaining translation artifacts. All 32 tests pass. The English translation of the codex-console project is now complete.

## My-RU-Coverage: rounds #35–#36

Two commits modify 51 files (715 insertions, 449 deletions).

### Round #35: generic wikilink elimination, anglicism replacement

72+ generic wikilinks replaced with specific Russian terms. 24 transliterated anglicisms swapped for native Russian equivalents (e.g., transliterated loanwords → established Russian terminology). Concrete wikilinks restored where generic ones had been used.

### Round #36: new classification categories, semiconductor cleanup

Two new classification categories introduced: `географический_объект` (geographic object) and `регулирование` (regulation). Semiconductor terminology cleaned up across skill files. Skill-file formatting corrections applied.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
