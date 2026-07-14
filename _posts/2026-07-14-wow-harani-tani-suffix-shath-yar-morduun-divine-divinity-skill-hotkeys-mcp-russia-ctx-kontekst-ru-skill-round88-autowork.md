---
title: "AUTOWORK - WoW Round 51: Hara'ni -tani species suffix, Shath'Yar Mor'duun; Divine Divinity skill hotkeys registered; mcp-russia ctx→kontekst (84 files); ru-skill round 88 hybrid terms"
date: 2026-07-14
layout: post
---

Four repositories see new commits on July 13–14: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Round 51 with Hara'ni's first linguistic investigation and a cross-language vocabulary entry, **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** resolves the Bevy parameter-limit blocker for skill hotkeys, **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies `ctx`→`kontekst` and `c`→`klient` across 84 files, and **[ru-skill](https://github.com/denis-gordeev/ru-skill)** eliminates hybrid terms in changesets and roadmap.

## wow_constructed_languages: Round 51 — Hara'ni Investigation 1 and Shath'Yar Mor'duun (121 insertions, 8 files)

### Hara'ni Investigation 1: The *-tani* Suffix in *Ruutani*

The first formal linguistic investigation for Hara'ni asks whether *-tani* in *Ruutani* (a Harandar-native species from the Midnight expansion) is a productive species-designation suffix. Wikipedia's consistent lowercase usage ("ruutani") supports it being a genuine Hara'ni common noun rather than a proper name.

Four decomposition options are evaluated:

| Decomposition | Analysis | Plausibility |
|---------------|----------|-------------|
| *Ruu-* + *-tani* | *-tani* = species/race designation suffix | Low–Moderate |
| *Ruut-* + *-ani* | *-ani* = collective suffix (variant of *-ni* with linking vowel) | Low–Moderate |
| *Ruuta-* + *-ni* | *-ni* = language/group suffix (as in *Hara'ni*) | Low |
| Monomorphemic | *Ruutani* is unanalyzable | Moderate |

If *-tani* belongs to the established suffix set (*-nir* = collective, *-ni* = language, *-ti* = faction), it would fill the "species/race" slot. Cross-linguistic comparison finds no confirmed parallel in Zandali, Darnassian, or Nerubian — making *-tani* potentially unique to Hara'ni. **Confidence: Low–Moderate**; single attestation limits confidence.

### Mor'duun: Cross-Language Vocabulary Entry

*Mor'duun*, leader of the Twilight's Blade cult in the Midnight campaign, is added to the Shath'Yar vocabulary. Its language affiliation is uncertain: the *Mor'* prefix parallels Zandali troll names, but the medial apostrophe is non-standard for Shath'Yar (which prefers initial apostrophe). Most likely Zandali or a mixed Zandali–Shath'Yar name, given the Twilight's Blade are mortal cultists in troll and elven territory. Also listed in zandali/vocabulary.md.

---

## open-divine-divinity-rust-bevy: Skill hotkeys registered via parameter consolidation (39 insertions, 34 deletions)

The previous round noted that `handle_skill_hotkeys` was unregistered due to Bevy 0.13's 16-parameter system limit (18 params). This commit resolves the blocker by consolidating `ComboState` and `LegendaryPassiveEffects` into the existing `PlayerSkills` resource:

```rust
struct PlayerSkills {
    skills: Vec<combat::CombatSkill>,
    combo_state: ComboState,          // moved from standalone Res
    legendary_effects: LegendaryPassiveEffects,  // moved from standalone Res
}
```

With two parameters removed, `handle_skill_hotkeys` now fits within the 16-parameter limit and is registered in the Update schedule. All six core combat systems are now active: `update_enemy_ai`, `process_damage_events`, `handle_player_basic_attack`, `handle_skill_hotkeys`, `handle_enemy_deaths`, `handle_player_death`. Downstream systems (`update_automap`, `update_combo_hud`, `update_legendary_passives`, `update_combo_timer`) updated to read from `Res<PlayerSkills>` instead of separate resources.

---

## mcp-russia: ctx→kontekst and c→klient across 84 files (1303 insertions, 1234 deletions)

The largest single commit in this round russifies two widespread English abbreviations and fixes a cekrf bug:

- **`ctx`→`kontekst`**: Every MCP tool function parameter renamed from `ctx: Context` to `kontekst: Context` across all 28 data modules and their corresponding test files. This is the most pervasive parameter in the codebase — every MCP tool takes a context parameter.
- **`c`→`klient`**: The cekrf client module variable renamed from single-letter `c` to `klient` for readability.
- **Bug fix**: `cekrf` `status`→`sostoyanie` (incomplete russification from a prior round).
- **Documentation**: CONTRIBUTING.md and README.md updated — "env vars"→"переменные окружения", "docstring"→"строка документации", "Conventional Commits"→"Конвенциональные коммиты", "Semantic Versioning"→"семантическому версионированию".

---

## ru-skill: Round 88 — Hybrid terms in changesets and roadmap (44 insertions, 34 deletions)

Round 88 eliminates Russian–English hybrid terms that mix both languages in a single phrase:

**In `.changeset/` (9 files)**:
- target-навык → целевой навык, target-пакет → целевой пакет
- legacy-пакеты → устаревшие пакеты
- на фикстурах → на эталонных данных
- skill-документацией → документацией навыка
- SSR-страницы → страницы с серверной отрисовкой (SSR)
- серверно отрендеренные → сгенерированные на сервере
- HTML-тесты → тесты HTML

**In `docs/roadmap.md` (3 replacements)**:
- серверно отрендеренных/ые → сгенерированных/ые на сервере
- User-facing guides → Пользовательские руководства

Also: `release-please` wrapped in backticks in python-packages/README.md; regression tests updated.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
