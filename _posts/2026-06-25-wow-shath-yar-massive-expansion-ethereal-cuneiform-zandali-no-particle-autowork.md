---
title: "AUTOWORK - WoW: Massive Shath'Yar expansion — 55+ confirmed phrases, pronoun system, syntax analysis; ethereal Zo'- prefix, cuneiform, Sufaadi; Zandali 'no' particle, Vol' prefix; codex-console-english artifact fixes; My-RU-Coverage round #46"
date: 2026-06-25
layout: post
---

**[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** receives its largest update yet: a massive Shath'Yar expansion with 55+ confirmed Blizzard-translated phrases, a reconstructed pronoun system, and preliminary syntax analysis. The ethereal vocabulary gains the *Zo'-* prefix (3 attestations), cuneiform writing confirmation, and the Sufaadi demonym. Zandali gets a *no* connective particle and *Vol* prefix analysis. Plus, 14 language description files receive Overview/Phonological Features/Writing System sections. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** fixes remaining translation artifacts. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** completes round #46.

## wow_constructed_languages: Massive Shath'Yar expansion

Four commits (2,213 insertions, 236 deletions, 67 files) transform Shath'Yar from "almost entirely unreconstructed" to a language with a confirmed pronoun system, dozens of attested phrases, and preliminary syntactic analysis.

### 55+ confirmed phrases with official Blizzard translations

All phrases come from in-game boss dialogue, quest text, and official Blizzard sources. Sources span the entire WoW expansion history:

- **Yogg-Saron / Ulduar**: *Uulwi ifis halahs gag erh'ongg w'ssh* = "The shadow of my corpse will choke this land for all eternity"
- **Yor'sahj the Unsleeping (Dragon Soul)**: 8 phrases including *Sk'yahf qi'plahf PH'MAGG!* = "Your soul will know ENDLESS TORMENT!" and *Shkul an'zig qvsakf KSSH'GA, ag'THYZAK agthu!* = "From its BLEAKEST DEPTHS, we RECLAIM this world!"
- **Mindflayer Kaahrj (Legion)**: 13 phrases including *Shath'mag vwyq shu et'agthu, Shath'mag sshk ye!* = "The Black Empire once ruled this pitiful world, and it will do so again!"
- **Warlord Zon'ozz (Dragon Soul)**: 11 phrases providing the richest source of *sk-** possessive forms
- **Mythrax / G'huun (BfA)**: 17 phrases with plague and corruption vocabulary
- **Vol'zith the Whisperer / Zek'voz**: Additional confirmed translations
- **Midnight expansion**: Deep Watcher phrases

### Pronoun system

The confirmed translations reveal a rich pronoun system:

| Person | Nominative | Accusative | Possessive |
|--------|-----------|-----------|------------|
| 1st singular | *y'za* | *hoq* | *za* (speculative: "my") |
| 2nd singular | *iilth* / *ilith* | — | *sk-* (prefix) |
| 1st plural | *ag* | — | *ak* |
| 3rd plural | *ywaq* | — | — |

The **possessive prefix *sk-*** is well-attested with six confirmed forms: *sk'magg* ("your suffering"), *sk'shgn* ("your fear"), *sk'shuul* ("your deaths"), *sk'tek* ("your skulls"), *sk'uuyat* ("your agony"), *sk'yahf* ("your soul(s)").

### Syntax: word order, negation, copula

The confirmed phrases now provide enough data for preliminary syntactic analysis:

- **Word order**: Predominantly SOV or VSO with significant flexibility — the wiki notes Shath'Yar grammar is "quite different from English, especially when it comes to articles and auxiliary verbs"
- **No articles**: Shath'Yar lacks "the" or "a/an"
- **Negation**: *maq* before the verb (*Ywaq maq oou* = "They do not die")
- **Copula**: *ma* = "is/are" (*Ywaq ma phgwa'cul hnakf* = "They are the whisper on the shivering wind")
- **Future tense**: Two markers — prefix *qi'* (*qi'uothk* = "will drown") and auxiliary *gag* (*Gag vwah gag yyqzz* = "You will all drown")

### Compound name decompositions confirmed

- **Shath'Yar** = *Shath* ("old/black") + *Yar* ("gods") — confirmed by *Shath'mag* = "Black Empire" and *Shath'gral* = "Old Ones"
- **Shuul'wah** = *shuul* ("death") + *wah* ("wing") = "Deathwing"

### Speculative dictionary and parser word list

A full speculative Shath'Yar–English dictionary is derived from cross-referencing confirmed phrases with translations, covering pronouns, nouns, verbs, adjectives, and prepositions. The in-game parser word list (languageID 178) provides a phonological inventory of 1–11 letter Shath'Yar-like forms.

---

## wow_constructed_languages: Ethereal vocabulary expansion

### The *Zo'-* prefix (3 attestations)

Three independent names share the *Zo'-* prefix, suggesting a genuine ethereal morpheme:

| Name | Decomposition | Context |
|------|--------------|---------|
| *Zo'Shuul* | *Zo'* + *-Shuul* | Overlook on K'aresh (Midnight) |
| *Zo'ardaz* | *Zo'* + *-ardaz* | Constable in Tazavesh |
| *Zo'ya* | *Zo'* + *-ya* | Pet on K'aresh |

The prefix appears in place names, personal names, and pet names — too broad a range for a single semantic gloss, but three independent attestations make it a likely genuine morpheme.

### Cuneiform writing confirmed

The K'areshi wiki confirms **K'areshi used cuneiform writing** — a wedge-shaped script impressed into clay tablets. This suggests an ancient, well-developed literary tradition predating the ethereal transformation.

### Sufaadi demonym and *-i* suffix upgrade

The city-state **Sufaad** has inhabitants called **Sufaadi**, providing a second independent attestation of the *-i* demonym suffix (after *K'areshi*), upgrading its confidence from Low–Moderate to Moderate.

### Domanaar species data and K'aresh lore

13 Domanaar names with IPA are added (Averzian, Pertinax, Enigmalia, Nocturnius, Charonus, Nysarra, Degentrius, Decimus, Nullaeus, Severum, Terminas, Vidious, Ziadan), with a systematic Latin-inspired vs. Arabic-inspired naming analysis. The Fallen-King Salhadaar section is added for the Midnight Voidspire raid.

---

## wow_constructed_languages: Zandali updates

### *no* connective particle

Three loa are attested with a **"no" connective particle** between a title element and the loa name:

| Name | Loa | Decomposition |
|------|-----|---------------|
| Elortha no Shadra | Spider loa | *Elortha* + *no* + *Shadra* |
| Eraka no Kimbul | Tiger loa | *Eraka* + *no* + *Kimbul* |
| Ueetay no Mueh'zala | Sandfury death loa | *Ueetay* + *no* + *Mueh'zala* |

This is the first evidence of a second preposition/particle beyond *na*. Possible meanings: genitive ("of"), vocative ("called"), or possessive.

### *Vol* prefix (3 attestations)

*Vol'jin*, *Vol'guk*, and *General Vol'tar* share the *Vol* prefix — possibly meaning "shadow" or "spirit" given Vol'jin's role as a shadow hunter, and the prefix's appearance in military contexts.

---

## wow_constructed_languages: 14 language description files

All 14 remaining language description files (draenei, eredun, kalimag, mogu, nature, nerglish, pandaren, sethrak, shalassian, taur-ahe, titan, tolvir, vulpera, common) receive structured Overview, Phonological Features, and Writing System sections, with HTML synced.

---

## codex-console-english: Remaining artifact fixes

One commit (4 files, 15 insertions, 4 deletions) fixes the last Chinese-English translation artifacts:

- `whether` → `True if` (Python conditional)
- `has been` → `was` (simplified past tense)
- `verification code` → `OTP` (accurate terminology in test)

---

## My-RU-Coverage: Round #46

One commit (21 files, 155 insertions, 129 deletions) replaces 8 loanword categories:

| Loanword | Russian replacement | Reports affected |
|----------|-------------------|-----------------|
| лидер | крупнейший / ведущий | 8 |
| мониторинг | контроль | DATA |
| инжиниринг-закупки-строительство | инженерно-закупочно-строительная модель | HYDR |
| дистрибутив | сборка | ASTR |
| Интернет-контент и информация | Интернет-информационные сервисы | YDEX + scripts |
| бизнес | направление | 3 scripts |
| контент | содержимое | 2 docstrings |

Tooling: `WIKILINK_ALIASES` expanded by 4 entries; network graph artifacts rebuilt.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
