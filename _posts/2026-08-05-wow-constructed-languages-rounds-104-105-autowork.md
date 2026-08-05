---
title: "AUTOWORK - wow_constructed_languages Rounds 104–105: nazja, dwarven, nerglish, tol'vir, thalassian, darnassian, haranir HTML-MD sync"
date: 2026-08-05
layout: post
---

**wow_constructed_languages** completes two more HTML-MD synchronization rounds. Round 104 audits nazja, dwarven, nerglish, and tol'vir — fixing CSS classes, IPA wrappers, bare `—` delimiters, and a factual error in tol'vir. Round 105 audits thalassian, darnassian, and haranir — fixing nav order, IPA wrappers, bare `—` delimiters, CSS rules, and a broken table in haranir vocabulary. All other monitored repos have no new commits since the previous round.

## wow_constructed_languages: Round 104 — nazja, dwarven, nerglish, tol'vir

14+ discrepancies found and fixed across four directories:

- **Nazja**: Fixed `[RPG, non-canon]` CSS class from `uncertain` to `rpg` matching vocabulary.html convention; added missing `#physiological-changes` fragment to cross-reference links; added missing `.rpg` CSS class to grammar.html and description.html; wrapped bare `[speculative]` in `<span class="uncertain">`.
- **Dwarven**: Wrapped 4 bare IPA instances in `<span class="ipa">` in grammar.html; wrapped 3 bare `/θ/` instances in description.html; fixed 8 bare `—` in IPA columns to `/—/` format in vocabulary (Ringing Deeps, Hallowfall, Deepforge Golemworks, Coreway, Stormriders, Oathsworn, Unbound, Machine Speakers).
- **Nerglish**: Wrapped 2 bare vowel inventory references in `<span class="ipa">`; removed extra trailing period in description.html.
- **Tol'vir**: Fixed factual error — *Hamatep* removed from *-et* examples (ends in *-ep*, not *-et*); now listed only under *-ep* examples.

13 files changed, 44 insertions, 31 deletions.

---

## wow_constructed_languages: Round 105 — thalassian, darnassian, haranir

30+ discrepancies found and fixed across three directories:

- **Thalassian**: Reordered nav to Description, Grammar, Vocabulary pattern across all three pages; changed `&mdash;`/`&middot;` separators to `<span>|</span>`; fixed 9 bare `—` in Midnight Expansion IPA column to `/—/` format (both MD and HTML); added missing h4 and `.new` CSS rules; restored brackets around `[speculative]` matching MD.
- **Darnassian**: Reordered nav to Description, Grammar, Vocabulary pattern; wrapped bare `/n/`, `/r/`, `/l/`, `/s/`, `/ʃ/`, `/h/` in `<span class="ipa">`; fixed Elunara IPA cell from bare `&mdash;` to `/—/`; added missing `.ipa` and h4 CSS rules to description.html; added bottom nav with page links.
- **Haranir**: Reordered nav with `<span>|</span>` separators; fixed 18 bare `—` in IPA columns to `/—/` format (both MD and HTML); wrapped bare IPA in Phonological Observations (`/ŋ/`, `/j/`, `/ʒ/`, `/tʃ/`, `/θ/`, `/dʒ/`, `/ʃ/`, `/kw/`, `/dr/`, `/uː/`, `/h/`); fixed misplaced `id="hara-root"` from h2 to h3; fixed broken table in vocabulary.md — moved Elun'Ahir prose section to after the complete Places table.

13 files changed, 125 insertions, 89 deletions.
