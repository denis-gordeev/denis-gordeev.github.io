---
title: "AUTOWORK - Five repos update: wow Round 127 (bare /uː/ in Harani), divine-divinity automap_panel + world_objects extraction (1504→1534 tests), ru-skill Round 128 (SSR формулировка), otclick SLSA provenance attestation, codex-console Round 113"
date: 2026-08-17
layout: post
---

Five monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## wow_constructed_languages: Round 127 — bare `/uː/` in Harani vocabulary

Continued IPA markup consistency sweep:

- **1 bare IPA instance** in haranir/vocabulary.html — long/geminate `/uː/` in Ruutani etymology note wrapped in `<span class="ipa">`
- **HTML quality verification**: no broken fragment links, no bare Unicode entities, all h2–h6 tags have id attributes, no duplicate IDs, no bare `<i>` tags, no bare asterisks in inferred/uncertain spans, no bare IPA outside `<span class="ipa">`
- No new WoW language data found — patch 12.1.5 still pending (Autumn 2026)

2 files changed, 7 insertions, 1 deletion.

---

## open-divine-divinity-rust-bevy: automap_panel + world_objects extracted, 1504→1534 tests

Continued game.rs decomposition — 2 more modules extracted:

- **automap_panel.rs** (1340 lines): AutoMap UI panel, tile rendering, fog of war, location markers, marker input, tooltips — 16 functions, 5 SystemParam types, 20 unit tests
- **world_objects.rs** (1840 lines): Interactive objects, drag mechanics, object animation, walkability updates, hidden items, faction locks — 27 functions, 2 SystemParam types, 30 unit tests (20 moved + 10 new)

game.rs: 22321→19219 lines (−3102 net). All 1534 tests pass, zero clippy warnings.

4 files changed, 4006 insertions, 3656 deletions.

---

## ru-skill: Round 128 — SSR формулировка выровнена

Periodic audit found and fixed 1 terminology inconsistency:

- **серверный рендеринг (SSR)** → **серверная отрисовка (SSR)** in README.md historical note (1 occurrence) — aligned with canonical Russian-first formulation
- All 23 tracked жаргонизмы confirmed not reverted in user-facing documentation

4 files changed, 24 insertions, 3 deletions.

---

## otclick: SLSA provenance attestation for published images

Supply-chain hardening continued — signing now targets immutable digest references with SLSA provenance:

- **Sign by digest**: images now signed using `RepoDigest` instead of mutable tags — `docker image inspect` extracts immutable reference after push
- **SLSA provenance attestation**: `cosign attest --type slsaprovenance` with predicate including buildType, source commit, pipeline/job IDs, resolved dependencies
- **Sigstore OIDC identity**: `SIGSTORE_ID_TOKEN` with `aud: sigstore` for keyless signing
- **Artifact dependency**: `sign-images` job consumes `image-references.env` artifact from `docker-push` for cross-job digest propagation
- **4 new CI regression tests** for digest-based signing and provenance attestation

4 files changed, 79 insertions, 15 deletions.

---

## codex-console-english: Round 113 — scan clean

Full scan found no translatable non-English content. Non-ASCII content limited to legitimate exceptions (UI emojis, `Türkiye` in test assertion). No Chinese-English calque patterns found. All 32 tests pass.

1 file changed (TODO.md).
