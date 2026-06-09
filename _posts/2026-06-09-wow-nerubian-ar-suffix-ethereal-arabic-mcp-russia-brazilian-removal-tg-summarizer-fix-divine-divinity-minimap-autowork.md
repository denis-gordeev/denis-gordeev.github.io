---
title: "AUTOWORK - WoW: nerubian -ar suffix, ethereal Arabic naming; mcp-russia: Brazilian modules removed; tg_summarizer: critical bug fix; Divine Divinity: visual minimap"
date: 2026-06-09
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository adds nerubian scroll text analysis, an -ar faction suffix investigation, and an ethereal Arabic-inspired naming pattern. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** deletes all 27 Brazilian modules entirely and wires the three new Russian government APIs. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** fixes a critical bug where summary failures were posted to Telegram as error strings. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies yandex-rasp and ktx_booking help text. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** completes Round 29 with a clean scan. The local **open-divine-divinity-rust-bevy** project adds a visual minimap, area dialogs, area quests, and inventory swap/comparison.

## wow_constructed_languages: scroll text, -ar suffix, Arabic naming

One commit adds 487 lines of linguistic analysis across nine files.

### Nerubian scroll text and -ar suffix (June 8)

The **nerubian/grammar.md** receives a full scroll text analysis covering orthographic conventions, phonological evidence, and morphological decomposition. An **-ar faction suffix** investigation documents five attestations at Low–Moderate confidence, while the **En- prefix** investigation remains at Very Low confidence with uncertain building origin.

### Earthen -oc/-roc element (June 8)

The **earthen/grammar.md** adds an investigation of the **-oc/-roc** element (two attestations, Very Low confidence), likely a Blizzard aesthetic choice rather than a productive morpheme.

### Ethereal Arabic-inspired naming pattern (June 8)

The **ethereal/grammar.md** documents an Arabic-inspired naming pattern: 9 out of 25 ethereal names follow this pattern, rated at **High confidence** for deliberate Blizzard design. This has significant implications for morpheme reliability, since names influenced by real-world language aesthetics may not decompose into genuine in-universe morphemes.

The alien-comparative.html and titan-forged-comparative.html pages are updated with corresponding sections, and HTML vocabulary files reflect all changes.

## mcp-russia: Brazilian modules fully removed, Russian APIs wired

The previous round disabled the 27 Brazilian modules; this commit **deletes them entirely** along with all their tests. This removes approximately 50,000 lines of Portuguese-language code. Concurrently, the three new Russian government modules receive real API connections:

- **Совет Федерации** (sovfed): multi-source fallback sovfed.ru/api → data.gov.ru → справочник
- **Федеральное казначейство** (kaznacheistvo): budget.gov.ru/api/v1 → roskazna.gov.ru/opendata
- **Росприроднадзор** (rosprirodnadzor): rpn.gov.ru/api → rpn.gov.ru/opendata → onv.register

Deprecated Brazilian aliases (format_brl, format_number_br, parse_brl_number) and validators (validate_cpf, validate_cnpj, validate_cep) are removed. Portuguese 'resultado ok' in tests is replaced with Russian 'rezultat ok'. Ruff config is cleaned up. **601 tests pass, 1 skipped.**

## tg_summarizer: critical bug fix and token usage logging

A critical bug is fixed: `summarize_text`/`summarize_group_text` previously returned an error string on failure, which was then posted to the Telegram channel and saved to history. Now they return `None` instead. The coverage check uses `.startswith('ДА')` instead of `== 'ДА'` for consistency. OpenAI token usage logging is added for cost monitoring. Elapsed seconds are added to the Lambda handler response. **9 new tests bring the total to 132, all passing.**

## ru-skill: yandex-rasp and ktx_booking russification

The yandex-rasp fallback value is russified, and the ktx_booking `--seat-option` help text is translated to Russian. The doc-regression test suite is expanded.

## codex-console-english: Round 29 clean scan

Round 29 scan complete — no new non-English text found, all 29 tests pass.

## open-divine-divinity-rust-bevy: minimap, dialogs, quests, inventory

A significant feature update adds a **visual minimap**, **area dialogs**, **area quests**, and **inventory swap/comparison** mechanics. Over 1,000 lines are added across game.rs, dialog.rs, layout.rs, and quests.rs.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
