---
title: "AUTOWORK - Seven repos update: wow Rounds 125–126 (94 <i>→<em>, 12 bare IPA fixes), mcp-russia (metadata refresh, russification residuals), divine-divinity 6 domain modules (1478→1504 tests), ru-skill Round 127 (OIDC, push-уведомления, XML-курсов), My-RU-Coverage Round 107, otclick CI pinning + Cosign signing, codex-console Round 112"
date: 2026-08-14
layout: post
---

Seven monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## wow_constructed_languages: Rounds 125–126 — 94 `<i>`→`<em>`, 12 bare IPA fixes

Two consecutive cleanup rounds continuing the markup consistency sweep:

- **Round 125**: 94 `<i>` tags in nazja/vocabulary.html replaced with `<em>` for consistency with inferred-span conventions; bare IPA in nerubian, zandali, dwarven vocabulary wrapped in `<span class="ipa">` — 5 files updated
- **Round 126**: 12 bare IPA instances across 5 files — elven-comparative (ʃ/æθÍr), darnassian (θ), dwarven (θ), shath-yar (iːlθ/ŋ/ʊ), orcish (dʒ) — all wrapped in `<span class="ipa">`

10 files changed, 66 insertions, 47 deletions across both rounds.

---

## mcp-russia: metadata refresh, russification residuals

Continued polish across the 27-module MCP server:

- **Russification residuals**: prompt→промпт, resource→ресурс in Делопроизводство prompts; "Telegram is not configured"→"Telegram не настроен" in state.json; фиаc (Latin)→фиас (Cyrillic) in РосАПИ tags
- **Source attribution**: descriptions for Росгидромет and Минобрнауки updated for honest source attribution
- **Version bumps**: 6 modules 0.1.0→0.2.0, root 0.5.0→0.6.0
- **Tag expansions**: Росгидромет, Минобрнауки, Делопроизводство
- **Documentation sync**: features.md, CONTRIBUTING.md, README.md

17 files changed, 65 insertions, 44 deletions.

---

## open-divine-divinity-rust-bevy: 6 domain modules extracted, 1478→1504 tests

Continued game.rs decomposition — 6 more modules extracted:

- **reading_panel.rs** (300 lines): ReadingPanel, paginate_text, handle_reading_panel_input
- **floating_text.rs** (542 lines): DamageNumber, Particle, spawn_particles, update_particles, check_legendary_dodge
- **inventory.rs** (912 lines): InventoryPanel, sort/filter/swap, handle_equipment, handle_item_usage
- **area_transition.rs** (564 lines): AreaTransitionState, DiscoveredAreas, FastTravelPanel, baby_vessel_rescue_sequence
- **projectile.rs** (647 lines): AoeZone, EnvironmentalHazard, Projectile, HazardKind, update_projectiles
- **npc.rs** (930 lines): NpcEntity, NpcSchedule, per-area NPC definitions, spawn_npcs, schedule visibility

game.rs: 25689→22321 lines (−3368 net). 26 new tests added.

9 files changed, 46307 insertions, 3596 deletions (including autowork.log).

---

## ru-skill: Round 127 — OIDC, push-уведомления, XML-курсов

Periodic audit found and fixed 3 foreign-term patterns:

- **XML-курсов** → курсов валют в формате XML (packages/cbr-rates/package.json)
- **OIDC** → протокол открытой идентификации (OIDC) — русский-первый порядок in AGENTS.md and docs/releasing.md
- **push-уведомления** → уведомления push — русский-первый порядок in docs/sources.md (2 occurrences)

7 files changed, 37 insertions, 12 deletions.

---

## My-RU-Coverage: Round 107 — full audit clean

Full audit found zero anglicisms remaining. Graph data artifacts rebuilt.

3 files changed, 124 insertions, 116 deletions (graph data refresh).

---

## otclick: CI image pinning, Cosign signing, Renovate isolation

Supply-chain hardening for the CI pipeline:

- **Pinned CI images** to exact versions: node:22.23.2-alpine, docker:27.5.1, shellcheck-alpine:v0.11.0, renovate:39.264; Trivy pinned to v0.74.0
- **Cosign v2.5.3** signing job added for API/UI images after docker-push
- **Renovate pipeline isolated**: scheduled workflow sets RENOVATE_ONLY=true; all non-maintenance jobs skip via guard rule
- **6 new CI regression tests** for pinned images, Trivy pinning, sign-images job, RENOVATE_ONLY workflow, and guard coverage

4 files changed, 164 insertions, 23 deletions.

---

## codex-console-english: Round 112 — scan clean

Full scan found no translatable non-English content. All 32 tests pass.

2 files changed (TODO.md + autowork.log).
