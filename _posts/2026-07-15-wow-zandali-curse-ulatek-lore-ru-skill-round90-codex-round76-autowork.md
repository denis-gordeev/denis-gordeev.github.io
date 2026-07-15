---
title: "AUTOWORK - WoW Zandali: Curse of Ula'tek lore (Kinduru death, Malacrass spirit mask), Hara'ni -ni cross-reference; ru-skill round 90 hybrid terms; codex-console round 76 verified English"
date: 2026-07-15
layout: post
---

Three repositories see new commits on July 14–15: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Round 55 with Curse of Ula'tek lore updates for Zandali and a Hara'ni cross-linguistic finding, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** eliminates hybrid terms in round 90, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** confirms full English compliance in round 76.

## wow_constructed_languages: Round 55 — Zandali Curse of Ula'tek lore and Hara'ni -ni cognate (19 insertions, 6 files)

### Zandali: Kinduru's Death and Malacrass Spirit Mask

The Curse of Ula'tek campaign (patch 12.1.0) brings major Zandali vocabulary and lore updates:

- **Kinduru killed**: The Loa Speaker was killed by the magic protecting the key to free Ula'tek, per Wikipedia's Curse of Ula'tek article. His vocabulary entry updated with confirmed family relationship (Zul'jin's son, not just Zul'jan's uncle) and death detail.
- **Malacrass spirit mask**: Hex Lord Malacrass disguised himself as an enchanted spirit mask knowledgeable of Ula'tek, deceiving Zul'jan and Kinduru. The spirit mask may be a *rush'kah* (ceremonial mask), the confirmed Zandali word for ritual masks — a potential linguistic connection between game lore and vocabulary.
- **Zul'jan expanded**: His vocabulary entry now includes the full Curse of Ula'tek arc — discovering the spirit mask, retrieving the key that kills Kinduru, and transforming into a "snakeoid beast" after seeking power.

### Hara'ni: Zandali *-ni* Cross-Reference

Investigation 1 in Hara'ni grammar adds a new cross-linguistic comparison: Zandali *Iklani* (an Amani villager name) ends in *-ni*, potentially analyzable as *Ikla-* + *-ni*. If Zandali *-ni* in personal names is cognate with Hara'ni *-ni* (language/group suffix), it would provide another cross-family morpheme connecting the two branches. However, *Iklani* is a single attestation and *-ni* could be part of the stem rather than a suffix. **Confidence: Very Low** for Zandali *-ni* as a cognate of Hara'ni *-ni*.

---

## ru-skill: Round 90 — Hybrid term elimination (33 insertions, 9 deletions, 5 files)

Round 90 targets Russian–English hybrid terms and calques that mix both languages in a single phrase:

- **`push-уведомления` → `уведомления push`** (2 occurrences in `docs/sources.md`): The English loanword is repositioned as a modifier after the Russian head noun, matching standard Russian typographic convention for borrowed technical terms.
- **`дата-диапазон` → `диапазон дат`** (2 occurrences in `docs/sources.md` and `docs/features/pravo-documents.md`): The hyphenated calque is replaced with natural Russian word order.
- Periodic audit of 10 key jargon terms confirms no regressions in SKILL.md, package README, or feature docs.
- Regression tests updated and passing.

---

## codex-console-english: Round 76 — Full English verification (9 insertions, 1 file)

Round 76 performs a comprehensive English compliance scan:

- Zero CJK/Cyrillic/non-translatable content found across all tracked source files.
- Non-ASCII content limited to legitimate exceptions: emojis (UI icons in HTML/JS), `Türkiye` in test assertion, `→` arrows in changelog notes.
- Deep scan for Chinese–English calque patterns (whether to, has been, obtain, according to, configuration, modal box, encapsulation, self-deployed, mailing list, private domain, interface current, execute, concurrencies, the number of, is not filled, fill in, is successful, passed in) — no new artifacts found.
- All 32 tests pass.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
