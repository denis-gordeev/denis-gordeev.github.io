---
title: "AUTOWORK - WoW phonological analysis Round 18, Divine Divinity storytelling objects, MCP-Russia deloproizvodstvo rename, RU-Coverage rounds 55–56, tg_summarizer EMF observability, Codex-Console round 59"
date: 2026-07-02
layout: post
---

Six repositories see new July 2 commits: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** delivers Round 18 with 57 phonological patterns across 14 languages, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** completes storytelling objects for all 10 areas, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** renames its last Portuguese directory and russifies ~250 variables, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** ships rounds #55 and #56, **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds CloudWatch alarms and expanded meta-artifact filters, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** finishes round 59.

## wow_constructed_languages: Round 18 — 57 phonological patterns, cross-language comparison

Three commits (866 insertions, 176 deletions, 45 files):

### Commit 1 — Cross-language phonological analysis, elven innovation

- Add 7 phonological patterns across 5 languages: Darnassian (post-apostrophe consonant preference), Thalassian (/ʃ/ initial dominance), Zandali (4 patterns including /z/ initial preference, /a/-monovocalic tendency), Orcish (back-vowel harmony), Shath'Yar (/q/ sound symbolism)
- Identify pre-apostrophe sonorant constraint as **elven innovation** (absent from Zandali and Orcish; confidence Low-Moderate → Moderate)
- Add head-stressed compounding as inherited Proto-Elven feature
- Full HTML↔MD sync audit across all 15 directories

### Commit 2 — Phonological patterns for 4 titan-forged languages

- Add Tol'vir (7 patterns), Vrykul (5), Draenei (6), Dwarven (4) phonological patterns
- Cross-language comparison rows in titan-forged-comparative.html (stress, clusters, vowel-initial, word-final)
- Fix Thero'shan condensed content in darnassian/grammar.html, Tenir→Tenvir typo

### Commit 3 — 46 patterns across 10 under-analyzed languages

- Shalassian (+5: sibilant avoidance, front vowel concentration), Nazja (+5: sibilant-initial dominance, -ess/-esh feminine), Eredun (+5: -oth Pit Lord suffix, Dreadlord vs Eredar split), Kalimag (+5: reduplication, fricative-final preference), Gutterspeak (+3: total phonological opacity), Earthen (+5: sibilant absence, compound name productivity), Nerubian (+5: voiceless obstruent finals, consonant echo), Qiraji (+5: heavy syllable preference, /ɑ/ dominance), Ethereal (+4: Z-initial names, post-vocalic /ʃ/), Hara'ni (+4: apostrophe syllable asymmetry)
- **Shalassian-Darnassian phonological conservatism score**: Shalassian 89% (8/9), Nazja 38% (3/8)
- **Vrykul-Dwarven gender-correlated final vowel**: three hypotheses evaluated; shared Norse design most likely
- Cross-language stress and word-final comparison added to README.md

---

## open-divine-divinity-rust-bevy: All 10 areas complete with storytelling objects

One commit (423 insertions, 8 deletions, 3 files):

- Add Book, Journal, and Statue objects to Castle Stormfist, Rivertown, Council Chambers, Imp's Chapel, and Wasteland (15 new lore objects)
- All **10 areas** now have complete Book/Journal/Statue coverage
- New `validate_dialog_markers()` warns on empty/invalid markers (QUEST, HAS, REWARD, SKILL, REP, XP, GOLD)
- 768 tests passing (was 763)

---

## mcp-russia: redator → deloproizvodstvo, ~250 variable russifications

One commit (9066 insertions, 255 deletions, 45 files):

- Rename last Portuguese directory `redator/` → `deloproizvodstvo/` (document-processing)
- Russify ~250 remaining English variables across 14 modules: rosstat, kad_arbitrazh, rosreestr, rosgidromet, rosapi, cekrf, gibdd, fssp, fns, gosduma, publikatsii, _shared/http_client, server
- Fix English words in templates (director, planned) and docs (your-key)
- ruff check: passed, pytest: 547 passed, 1 skipped

---

## My-RU-Coverage: Rounds #55 and #56

### Round #55 (147 insertions, 119 deletions, 18 files)

| Loanword | Russian replacement |
|----------|-------------------|
| маржинальный | рентабельный |
| последняя миля | завершающий участок доставки |
| вертикаль | направление |
| роутер | маршрутизатор |
| корпоративные клиенты/заказчики | из числа предприятий |
| Сервисные металлоцентры | Металлоцентры с обработкой проката (MAGN) |

### Round #56 (150 insertions, 126 deletions, 20 files)

- локальный → местный/внутренний/российский across 6 reports
- Stale skill-file keys updated, enrichment JSON refreshed

---

## tg_summarizer: CloudWatch alarms, EMF observability, prompt compaction

One commit (383 insertions, 57 deletions, 7 files):

- **CircuitBreakerHalfOpenAlarm** and **DLQDepthAlarm** added to template.yaml
- `CircuitBreakerState` EMF metric (0=closed, 1=half_open, 2=open) emitted per invocation
- CloudWatch dashboard widget for circuit breaker state
- Prompt compaction: `CHANNEL_SUMMARY_PROMPT` and `GROUP_SUMMARY_PROMPT` rules consolidated (same content, fewer tokens)
- Meta-artifact filters expanded: ~20 new Russian filler phrases (исходя из вышесказанного, нужно отметить, очевидно, безусловно, etc.) plus резюме/сводка/главное/основное labels
- `_emit_emf` now logs failures instead of silently swallowing exceptions
- 30+ new/updated tests (452 → ~480 total)

---

## codex-console-english: Round 58–59

Two commits:

- **Round 58**: Replace remaining `configuration` → `settings` in Dockerfile, constants, and Outlook service (15 insertions, 3 deletions, 4 files)
- **Round 59**: Verify translation complete, update TODO.md

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
