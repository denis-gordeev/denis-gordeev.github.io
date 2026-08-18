---
title: "AUTOWORK - Six repos update: divine-divinity crafting/enchanting/stats panels (1534→1566 tests), ru-skill Round 129 (поверхность→интерфейс, legacy→устаревший, hybrids→Russian-first), otclick digest-pinned CI + verify-signatures gate, mcp-russia metadata refresh 0.5.0→0.6.0, My-RU-Coverage Round 108 (контур→система/направление, масштабировать→наращивать, wikilink cases), codex-console Round 113 scan clean"
date: 2026-08-18
layout: post
---

Six monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content). wow_constructed_languages has no new commits.

## open-divine-divinity-rust-bevy: crafting_panel, enchanting_panel, stats_panel extracted, 1534→1566 tests

Continued game.rs decomposition — 3 more modules extracted:

- **crafting_panel.rs** (469 lines): CraftingPanel, CraftingPanelText, spawn/toggle/update/input, craft attempt, faction gold cost/success chance helpers, 10 unit tests
- **enchanting_panel.rs** (702 lines): EnchantingState, EnchantingPanel, EnchantingPanelText, spawn/toggle/update/input, enchant validation/attempt, material count/consume, 12 unit tests
- **stats_panel.rs** (417 lines): CharacterStatsPanel, StatsHeaderText/Attributes/Skills/Inventory, CharacterStatsPanelData, spawn/toggle/update, reputation_label, format_attributes/skills/inventory, 10 unit tests

game.rs: 19219→18079 lines (−1140 net). All 1566 tests pass, zero clippy warnings.

5 files changed, 1707 insertions, 1269 deletions.

---

## ru-skill: Round 129 — поверхность→интерфейс, legacy→устаревший, English-first hybrids→Russian-first

Periodic audit found and fixed terminology inconsistencies in skill-docs.test.js:

- **поверхность → интерфейс**: 24 occurrences in test names and assertion messages — calque from "surface" replaced with natural Russian term
- **legacy → устаревший/устаревших/устаревшая**: ~21 occurrences in test names and assertions — English jargon replaced with Russian equivalent
- **English-first hybrids → Russian-first**: ~28 occurrences — `npm-скрипт` → `скрипт npm`, `Python-хелпера` → `вспомогательного скрипта Python`, `workspace-пакеты` → `пакеты рабочего пространства`, `shell-скрипты` → `скрипты оболочки`, `target-пакетов` → `целевых пакетов`, `inline-характеристики` → `встроенные характеристики`, `anchor-точка` → `опорная точка`, `booking-навыков` → `навыков бронирования`, `amenity-типы` → `типы заведений`, and others
- **CI → система непрерывной интеграции (CI)**: 1 occurrence in docs/roadmap.md — added Russian clarification
- All 23 key tracked jargon terms confirmed not reverted in user-facing documentation

3 files changed, 115 insertions, 91 deletions.

---

## otclick: digest-pinned CI images, verify-signatures gate, immutable deploy refs

Supply-chain hardening continued — CI pipeline now fully digest-pinned with fail-closed signature verification:

- **Digest-pinned CI images**: all 7 CI images pinned by sha256 digest (alpine, python, node, docker, docker-dind, shellcheck, renovate); Renovate `pinDigests: true` keeps them updated automatically
- **verify-signatures job**: fail-closed Cosign signature + SLSA provenance verification before any deployment; `deploy:staging` depends on `verify-signatures` + `docker-push`
- **Immutable deploy refs**: webhooks now send `RepoDigests` instead of mutable tags; deploy jobs receive `image-references.env` dotenv from `docker-push`
- **4 new pytest regressions**: digest pinning, verify-signatures gate, immutable deploy refs, Renovate pinDigests config

5 files changed, 133 insertions, 35 deletions.

---

## mcp-russia: metadata refresh — 0.5.0→0.6.0, tool names, comments

Version references and documentation updated across the codebase:

- **Version bump**: `0.5.0` → `0.6.0` in feature.py, lifespan.py, settings.py docstrings
- **Tool name fix**: `poisk + poluchit_tegi + vypolnit` → `teg + poisk + poluchit_skhemy` in settings.py — aligned with current API
- **Comment improvements**: `istochnik` → `источник:` in publikatsii/schemas.py, `sostoyanie` enum values in Russian in rospotrebnadzor/schemas.py

7 files changed, 14 insertions, 6 deletions.

---

## My-RU-Coverage: Round 108 — контур→система/направление/комплекс, масштабировать→наращивать, wikilink grammatical cases

Major calque elimination round across 12 company reports:

- **контур → система/направление/комплекс/состав/среда/рынок**: 21 occurrences in 12 reports — systematic calque from "circuit/loop" replaced with context-appropriate Russian terms (e.g., `контур перевозок и хранения` → `система перевозок и хранения`, `экспортный контур` → `экспортное направление`, `единый операционный контур` → `единая операционная среда`, `российского контура` → `российского рынка`)
- **масштабировать → наращивать**: 1 occurrence in DOMRF report — calque from "scale" in business context replaced with natural Russian equivalent
- **Wikilink grammatical case fixes**: 5 occurrences in 4 reports — systematic error of nominative case after prepositions corrected (e.g., `у [[Газпром]]` → `у [[Газпром|Газпрома]]`, `с [[Фармстандарт]]` → `с [[Фармстандарт|Фармстандартом]]`)
- **24 alias entries** added to wikilink alias dictionary to prevent re-introduction
- All 43/43 reports pass quality audit; all 13 scripts compile without errors

22 files changed, 188 insertions, 134 deletions.

---

## codex-console-english: Round 113 — scan clean (no new code changes)

Full scan found no translatable non-English content. Non-ASCII content limited to legitimate exceptions (UI emojis, `Türkiye` in test assertion). No Chinese-English calque patterns found. All 32 tests pass.

1 file changed (TODO.md updated).
