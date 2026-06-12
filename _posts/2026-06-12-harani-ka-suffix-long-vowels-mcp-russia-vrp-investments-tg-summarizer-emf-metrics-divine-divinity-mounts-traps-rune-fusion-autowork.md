---
title: "AUTOWORK - WoW: Hara'ni -ka suffix, long vowels, Shay'neia; MCP-Russia: ВРП by ОКВЭД, investments; tg_summarizer: EMF metrics; Divine Divinity: mounts, traps, rune fusion; ru-skill: test russification; codex-console: auth coverage"
date: 2026-06-12
layout: post
---

The **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** repository deepens Hara'ni morphological analysis with three new suffix studies (-ka agentive, -neia/-leia/-iea feminine endings, long /uː/ vowel confirmation). **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** adds GRP industry structure by ОКВЭД and investment breakdowns by activity type. **[tg_summarizer](https://github.com/denis-gordeev/tg_summarizer)** gains CloudWatch EMF latency metrics, anti-repetition prompts, and config hardening. **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds mount/fast travel, trap dungeon rooms, and rune fusion. **[ru-skill](https://github.com/denis-gordeev/ru-skill)** russifies ~90 JS and 19 Python test descriptions. **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** improves webui auth redirect test coverage.

## wow_constructed_languages: Hara'ni morphological deepening

One commit adds 139 insertions, 21 deletions across 7 files — a focused deepening of Hara'ni grammar and vocabulary.

### -ka suffix: from "hunter" to "entity/personification"

The *-ka* suffix, previously known only from *Shul'ka* ("Hunters of Shadows"), now appears in *Morta'ka* ("the Sundered Echo"). Three interpretations are evaluated: (1) *-ka* = "hunter(s)" — confirmed for *Shul'ka* but semantically inconsistent with *Morta'ka* (an adversary, not a hunter); (2) *-ka* = "entity/personification of [X]" — semantically consistent with both attestations; (3) *-ka* = "severed/ritually bonded one" — creatively consistent but requires assuming a ritual-specific suffix. The broad agentive/personification interpretation is preferred. Confidence: Very Low–Low.

### -neia / -leia / -iea: one suffix or three?

The Zur'ashar member *Shay'neia* adds a third *-ia*-variant ending to the corpus, alongside *Ney'leia* (-leia) and *On'hiea* (-iea). Analysis shows these do NOT represent three distinct suffixes but rather three name stems followed by a single *-a* feminine suffix (*Shay'nei* + *-a*, *Ney'lei* + *-a*, *On'hi* + *-a*). The variation is in the stem, not the suffix. This is the more parsimonious analysis.

### Long /uː/ vowel confirmed

*Fuunid* (-uu-) and *Ruutani* (-uu-) now provide two independent attestations of long/geminate /uː/, confirming it as a genuine Hara'ni phonological feature rather than a spelling error. The *Ruutani* spelling is resolved: Wikipedia consistently uses "ruutani" (lowercase common noun), supporting both the double-u spelling and the hypothesis that *ruutani* is a genuine Hara'ni word. Confidence for *Ruutani* as Hara'ni: upgraded from Very Low–Low to Low–Moderate.

### Updated corpus counts

The Hara'ni corpus now contains ~16 personal names (up from ~12), ~14 place names (up from ~3), ~11 cultural/faction names (up from ~5), and 3 Midnight-era terms (*Ruutani*, *Alndust*, *Shay'neia*).

## mcp-russia: ВРП industry structure and investments by ОКВЭД

Two commits add 699 insertions, 36 deletions across 24 files — the largest update since the ЕМИСС tool.

### Отраслевая структура ВРП

A new `otraslevaya_struktura_vrp` tool provides GRP (ВРП) breakdown by ОКВЭД sections, with values in billions of rubles and share percentages. Supports both national and regional queries. Falls back to fedstat.ru/ЕМИСС links when live data is unavailable.

### Инвестиции по видам деятельности

A new `investitsii_po_vidam` tool provides investment in fixed capital by economic activity type (ОКВЭД). Includes a dedicated constants file with activity categories, a new schema for investment data, and 107 new test lines for Rosstat tools.

### Documentation cleanup

Portuguese test fixtures removed, CONTRIBUTING.md and guide/reference docs updated.

### Auth environment variables for Госдума/Закупки/РосАПИ

Auth environment variables (`auth_env_var`) added for Госдума, Закупки, and РосАПИ tools. An `AuthError` exception introduced in rosapi for clear auth-failure messages. Discovery and feature modules updated to surface auth requirements. 47 new test lines across gosduma, rosapi, and zakupki test suites.

## tg_summarizer: EMF latency metrics and hardening

One commit adds 292 insertions, 27 deletions across 12 files (7 new tests, total 173).

### CloudWatch EMF latency metrics

`call_openai` now emits an Embedded Metric Format (EMF) JSON to stdout on every OpenAI API call. The metric includes latency, model name, token count, and Lambda function name — automatically ingested by CloudWatch with no additional API calls or dependencies.

### Anti-repetition prompts

Prompts updated to reduce repetitive summaries across runs.

### Config hardening

`RESTORE_TIMEOUT_SEC` added as a configurable environment variable (default 30s, rejects zero). S3 sync and history manager receive improved error handling. Dead code removed.

## open-divine-divinity-rust-bevy: mounts, traps, rune fusion

One commit adds 1,446 insertions, 92 deletions across 3 files — a major gameplay systems update.

### Mount and fast travel system

Players can mount a Horse (1.6x speed) or War Wolf (1.4x speed). Mounts are outdoor-only; underground areas (catacombs, Black Ring Fortress, Council Chambers) revert to walking speed. A fast travel panel allows teleportation to previously discovered areas. An area discovery tracker records visited locations.

### Trap dungeon mechanics

Three trap room types: Poison Gas (damage-over-time zone), Collapsing Floor (tiles with delay-triggered collapse), and Timed Escape (countdown puzzle with XP/gold reward). A `TrapRoomState` resource tracks active trap progress.

### Rune fusion system

A `CompositeRune` system allows combining two runes into a more powerful one: Sigil of Might + Rune of Fortitude → Rune of the Titan (+8 strength), Glyph of Arcana + Glyph of Insight → Rune of the Archmage (+8 intelligence), and three more combinations. A rune combo panel UI handles selection and fusion.

## ru-skill: test description russification

One commit modifies 11 files (254 insertions, 179 deletions).

~90 JavaScript test descriptions in `skill-docs.test.js` and 19 Python test descriptions (`test_fine_dust.py`, `test_ktx_booking.py`) translated to Russian. Section headers changed from `## API` to `## API-справочник`. The `doc-regression` test suite expanded to verify English test descriptions and API headers.

## codex-console-english: auth redirect coverage

One commit adds 60 insertions, 3 deletions across 4 files. WebUI auth redirect receives expanded test coverage (42 new tests in `test_app_lifespan.py`). README and TODO updated.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
