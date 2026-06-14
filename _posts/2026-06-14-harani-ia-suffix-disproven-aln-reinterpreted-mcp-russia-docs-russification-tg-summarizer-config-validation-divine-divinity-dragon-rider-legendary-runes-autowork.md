---
title: "AUTOWORK - WoW: Hara'ni -ia suffix disproven, *Aln-* reinterpreted; MCP-Russia: ~160 file docstring russification, ЕМИСС fixes; tg_summarizer: float config, prompt optimization; Divine Divinity: dragon rider, legendary runes, trap resolution; ru-skill: assert russification; codex-console: Agent→Proxy fix; My-RU-Coverage: Russian category keys"
date: 2026-06-14
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository resolves three open Hara'ni questions: the *-ia* feminine suffix is effectively disproven (Ruia and On'hiea confirmed male), the *Aln-* root is reinterpreted as "deep/source/rift" (Moderate confidence), and the Midnight alpha mural text is confirmed non-canon. **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** completes a massive russification pass across ~160 Python files, fixes two broken ЕМИСС codes, and fills in real 2022 ВРП/инвестиции static data. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** adds validated float config, simplifies coverage+match prompts (≈30% token savings), and hardens Lambda deadline handling. **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** introduces dragon rider mounts, legendary triple-rune fusion, and trap resolution mechanics. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies ~107 assert messages and top-level document headings. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** fixes the systematic Agent→Proxy mistranslation and polishes English copy. **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** translates category/role/profile keys to Russian and reclassifies wikilinks (MOEX, Kaspersky, VK Cloud, YADRO → российские).

## wow_constructed_languages: three Hara'ni questions resolved, ethereal expansion

Two commits add 284 insertions, 132 deletions across 13 files.

### *-ia* feminine suffix: effectively disproven

Wiki gender icons confirm Ruia and On'hiea are both male. With 2 of 3 *-ia*-ending names male, the feminine suffix hypothesis cannot stand. The *-ia* ending is either gender-neutral or coincidental Blizzard aesthetics. The *Shay'neia* analysis confirms stem + final *-a* decomposition (variation in the stem, not the suffix).

### *Aln-* root: "sacred" → "deep/source/rift"

The *Aln-* root is reinterpreted from "sacred/hallowed" to "deep/source/rift" with Moderate confidence, supported by four attestations (*Aln'hara* = "Worldsoul of Azeroth" confirmed, *Alndust*, *Rift of Aln*, *Alnscorned*) and one confirmed translation.

### Midnight alpha mural: non-canon

The alpha build mural depicting Haranir as progenitors of all trollkind was changed at launch to a "split" in Haranir society. The alpha text is no longer canon and contributed no Hara'ni vocabulary.

### Silversun Compact, Dreamrift, ethereal additions

A Silversun Compact faction name is added to Thalassian vocabulary (portmanteau of Silver Covenant + Sunreavers). The Dreamrift raid expands Shul'ka lore: they hunt an "undreamt god" across the dream/reality boundary. Ethereal vocabulary gains Imperator Averzian and a Salhaadar/Salhadaar spelling variant from the Midnight Voidspire raid.

## mcp-russia: total docstring russification, ЕМИСС code fixes, static data

One commit modifies 167 files (739 insertions, 507 deletions).

### ~160 file docstring russification

All module docstrings across `src/mcp_russia/` translated to Russian: `_shared/` (9 modules), `data/` (22 modules × ~7 files each), `agenty/` (5 files), plus 30 key function docstrings (rosstat, rosgidromet, publikatsii, gosduma, fns, _shared).

### ЕМИСС code verification and fixes

Two broken ЕМИСС codes discovered and replaced: `energy_production` 31110 → 31208 (old code pointed to an obsolete agricultural price index), `transport_cargo` 31153 → 31221 (old code pointed to enterprises with overdue debt). Four more codes marked as ⚠️ obsolete (fedstat.ru shows empty placeholder pages).

### Real 2022 static data for ВРП and investments

`OTRASLEVAYA_STRUKTURA_VRP` and `VIDY_DEYATELNOSTI_INVESTITSII` now contain actual Росстат data for all 19 ОКВЭД sections (ВРП 2022 ≈ 135 539 млрд ₽, инвестиции ≈ 28 949 млрд ₽), replacing null fallback values.

### CHANGELOG cleanup

Legacy tags added: `tabua_mares → tabua_mares (legacy)`, `compras/pncp → compras/pncp (legacy)`.

## tg_summarizer: float config validation, prompt optimization, deadline hardening

One commit adds 209 insertions, 29 deletions across 8 files (10 new tests, total 183).

### `_get_float_env()` for validated float config

New `config._get_float_env()` mirrors `_get_int_env()` with range bounds. Applied to `OPENAI_SUMMARY_TEMPERATURE` (0.0–2.0), `SIMILARITY_LLM_LOWER` (0.0–1.0), `SIMILARITY_LLM_UPPER` (0.0–1.0), replacing raw `float(os.getenv(...))` calls.

### Coverage+match prompt simplification

Removed duplicated instructions from `_check_coverage_and_match` user_content that repeated the system prompt. Saves ≈30% input tokens per coverage check. Prompt tightened: "существенные детали" → "существенные **новые** детали."

### Deadline hardening and summary length enforcement

A deadline check added to the covered message processing loop prevents Lambda timeouts when many messages need sequential LLM calls + Telegram edits. Summary edits now enforce length limits via `enforce_summary_length()`. `_create_summary_info()` made sync (was needlessly async). OpenAI client reset on 401/403 auth errors.

## open-divine-divinity-rust-bevy: dragon rider, legendary runes, trap resolution

One commit adds 1,083 insertions, 108 deletions across 4 files (26 new tests, total 476).

### Dragon rider mount

`MountType::Dragon` with 2.5x speed, no outdoor restriction. Unlocked via Dragon Saddle found in Dragon Rider's Lair. Dragon can fast travel to any area including underground.

### Legendary (triple-rune) fusion

5 legendary recipes combining three runes into items with dual stat bonuses and passive effects: Colossus (+12 STR, +80 HP, HP regen), Oracle (+12 INT, +10 CHA, trap reveal), Vanguard (+8 DEX, +6 STR, dodge), Bastion (+100 HP, +8 CON, damage reduction), Enlightened (+10 WIS, +8 INT, mana cost reduction). Ctrl+number selects third rune.

### Trap resolution mechanics

`GasValve` component (shut off poison gas with Valve Handle), `PlankItem` (bridge collapsing floors), `SpeedShrine` (bonus time in timed escapes). `TrapResolutionMethod` enum tracks how each trap was resolved.

## ru-skill: assert message russification, heading translations

One commit modifies 12 files (227 insertions, 174 deletions).

~107 English assert messages in `skill-docs.test.js` translated to Russian. Top-level document headings russified: `# Brand Inventory` → `# Инвентарь бренда`, `# Sources` → `# Источники`, `# Roadmap` → `# Дорожная карта`. English jargon eliminated from feature docs: `production` → `промышленного использования`, `live-` → `в реальном времени`, `discovery` → `обнаружение`, `export` → `экспорт`. Doc-regression expanded with new tests.

## codex-console-english: Agent→Proxy fix, English copy polish

Two commits modify 41 files (524 insertions, 501 deletions).

The systematic Agent→Proxy mistranslation (Chinese 代理 meaning "proxy" not "agent") is corrected across settings, constants, routes, models, crud, and upload modules. `Mailbox→Email` normalization applied across services, routes, and docstrings. Awkward literal translations replaced with natural English (tempmail, websocket messages). Rate limiting terminology fixed ("current limiting" → "rate limiting"). Standardized error messages ("does not exist" → "not found").

## My-RU-Coverage: Russian category keys, wikilink reclassification

One commit modifies 9 files (174 insertions, 156 deletions).

Category keys in `utils.py` translated: `local_company` → `локальная_компания`, `international_company` → `иностранная_компания`, `technology` → `технология`, `material` → `материал`, `application` → `конечный_рынок`. Role and profile keys in `build_themes.py` and `discover.py` similarly translated. Wikilink classification fixed: MOEX, Kaspersky, VK Cloud, YADRO, Selectel moved from "Иностранные компании" to "Российские компании". Legacy term "подложка" replaced with "сырьё". CLAUDE.md section headings translated to Russian.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
