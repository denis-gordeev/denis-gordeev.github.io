---
title: "AUTOWORK - WoW Rounds 56-58: Zandali -darah cognate, Ethereal Zo'- prefix, Shath'Yar Domanaar Latin names; Divine Divinity animation frames; mcp-russia test russification; ru-coverage rounds 73-74; ru-skill round 91; codex round 77"
date: 2026-07-16
layout: post
---

Six repositories see new commits on July 15–16: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships three rounds (56–58) with major cross-family cognate analysis, a new ethereal prefix, and Domanaar Latin-style naming in Shath'Yar; **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds object animation frame catalog lookup with clippy cleanup; **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** completes test data russification and Portuguese artifact removal; **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** eliminates the "решение" calque in rounds 73–74; **[ru-skill](https://github.com/denis-gordeev/ru-skill)** removes redundant terms in round 91; and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** confirms full English compliance in round 77.

## wow_constructed_languages: Rounds 56–58 (435 insertions, 18 files)

### Round 56: Zandali Investigation 13 — *-darah* cross-family cognate with Elven *-dorah*/*-dora*

The loa name *Akil'darah* (Patch 12.1.0, Coiled Isle) decomposes as *Akil'* ("eagle") + *-darah*. The *-darah* element shows a striking phonological parallel with the elven morpheme family: Darnassian *-dorah* (honor/remembrance), Shalassian *-dora* (grace/thanks), and Thalassian *-dorah* (honor). The consonantal skeleton /d-r-h/ is identical across all four languages, and the vowel shift from elven /o/ to Zandali /a/ is consistent with Zandali's well-documented /a/-dominance tendency. If confirmed, *-darah* would be only the **second cross-family morpheme** shared between Zandali and the elven languages (after *-da*, Investigation 6). **Confidence: Low–Moderate** — the single Zandali attestation and lack of confirmed gloss prevent firm conclusions.

Two new phonological patterns are also documented:
- **Pattern 17: Reduplication** — The loa name *Dundun* exhibits total reduplication (*Dun* → *Dundun*), the first attested Zandali reduplication, paralleling qiraji *Sarsarun* and Shath'Yar *gag gag*.
- **Pattern 18: Initial *Q'*** — The loa *Q'onzu* contains initial *Q* (otherwise unattested in Zandali), potentially reflecting Shath'Yar/Aqir substrate influence on loa nomenclature.

### Round 57: Ethereal Investigation 3 — *Zo'-* prefix (3 attestations)

Three independent ethereal names share the initial element *Zo'-*: place name *Zo'Shuul* (Overlook on K'aresh), personal name *Zo'ardaz* (Constable in Tazavesh), and pet name *Zo'ya*. The cross-category distribution (places, people, pets) is unusual — most WoW morphemes are restricted to one category. Hypotheses range from a demonstrative/definite article ("this place", "this person") to a personal name used in associative naming ("Zo's Overlook"). All three names are from Midnight/K'aresh content, so the Blizzard design-convention confound cannot be ruled out. **Confidence: Moderate** that *Zo'-* is a genuine morpheme; **Very Low** on specific meaning.

### Round 58: Shath'Yar Investigation 17 — Domanaar Latin-style naming

The Midnight expansion introduces the **domanaar**, generals of the Devouring Host: *Decimus* and *Terminas*. Both names follow Latin morphological patterns (*decimus* = "tenth"; *terminus* = "boundary/end"), which is anomalous in the Shath'Yar naming system with its pervasive apostrophes and heavy consonant clusters (*ssh*, *qzz*, *thk*). The most likely explanation is a Blizzard design choice paralleling Eredun Latinate naming for Legion commanders (*Archimonde*, *Kil'jaeden*) — Latinate names evoke imperial authority and hierarchy for void aristocracy. **Confidence: Moderate–High** for design-driven rather than genuine Shath'Yar morphology.

---

## open-divine-divinity-rust-bevy: Object animation frames catalog name lookup (250 insertions, 15 files)

The latest commit adds catalog name keys to `try_load_object_animation_frames()` with optional `ObjectCatalog` parameter and global ID mapping, plus fuzzy name matching (exact, case-insensitive substring) in `get_object_anim_frames()`. The `spawn_interactive_objects()` function now uses catalog names for animation frame lookup between `obj_anim_{index}` and `kind-name` keys. Additionally, 95 clippy warnings were fixed (143→48 remaining, all structural Bevy limits), and 3 new tests were added (927→930 total).

---

## mcp-russia: Test data russification, Portuguese artifact removal (177 insertions, 19 files)

This commit russifies test data and removes Portuguese artifacts from earlier data imports:

- Portuguese artifacts replaced: `uf/SP/RJ` → `subiekt/77/16`
- Test function names russified: `env_var_set` → `s_peremennoy_okruzheniya`, etc.
- String literals in tests russified (~40 replacements)
- JSON key `instrument` → `imya_instrumenta` in batch.py/server.py
- Documentation russified: Mock→Мок, e2e→сквозное, PR→пул-реквест, production→рабочие
- Outdated constant `ROSSTAT_API_BASE` → `EMISS_BAZA_API`
- All 630 tests pass, 1 skipped; ruff check/format clean.

---

## My-RU-Coverage: Rounds 73–74 (274 insertions, 25 files)

### Round 73: Calque elimination

- **интернет вещей → подключённые устройства** (Internet of Things → connected devices)
- **индустриальные → промышленные** (industrial calque correction)
- Grammar fixes in DATA sector reports

### Round 74: "решение" calque + moex_status.py russification

- **"решение" (from "solution") → context-appropriate Russian**: 20 occurrences across 15 reports — the calque was used where Russian has native alternatives like "вариант", "разрешение", or "ответ" depending on context
- **"содержание" → "контент"** in digital context (5 occurrences)
- **moex_status.py** russified: ~20 variables converted to Russian identifiers
- Wikilink aliases updated across 19 company reports

---

## ru-skill: Round 91 — Redundant term removal (18 insertions, 5 files)

Round 91 eliminates redundant and duplicated entries:

- **CAPTCHA** removed as redundant (the Cyrillic term "капча" is already listed)
- **SSR** and **серверная отрисовка** de-duplicated (both refer to the same concept)
- Regression tests updated and passing

---

## codex-console-english: Round 77 — Full English verification (16,459 insertions, 2 files)

Round 77 confirms full English compliance: zero CJK/Cyrillic/non-translatable content found. All 32 tests pass. The large diff is due to autowork.log growth (not source changes).

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
