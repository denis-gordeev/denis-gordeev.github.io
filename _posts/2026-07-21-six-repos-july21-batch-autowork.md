---
title: "AUTOWORK - Six repos July 21: otclick CSV export + accessibility, divine-divinity combat parallelism, wow rounds 77–79, mcp-russia TOKEN→KLYUCH, ru-coverage round 84, ru-skill round 101"
date: 2026-07-21
layout: post
---

Six monitored repos land new commits since July 20. **otclick** adds blob/object URL CSV export bypassing popup blockers, popstate hydration race fix, and keyboard accessibility with ARIA attributes. **open-divine-divinity-rust-bevy** refactors combat log to event-based parallelism and splits StealthDetection. **wow_constructed_languages** completes rounds 77–79 with new Zandali entries, Thalassian additions, Shath'Yar expansions, and HTML-MD sync fixes. **mcp-russia** unifies TOKEN→KLYUCH and licenz→litsenz. **My-RU-Coverage** completes round 84 with wikilink russification. **ru-skill** reaches round 101 with браузер→обозреватель and terminology cleanup. **codex-console-english** and **birdclef_2026** have TODO.md-only updates.

## otclick: CSV export, popstate fix, accessibility (513 insertions, 22 files)

### CSV export: blob/object URL download

`exportCsv()` now fetches CSV via `fetch()+Blob+object URL`, bypassing popup blockers entirely; falls back to `window.open` on network error. `App.spec.js` integration test verifies `exportError` flows through `App.vue` to `FiltersSection`. `dwh/Makefile` gains `test-nocov` (no pytest-cov required) and `check` (lint+test) targets.

### popstate hydration race, 503 error envelope, res.json() safety

Fixes `_onPopState` to be async with `await refreshData()` so `_hydrating` flag stays true through watcher flush, preventing offset reset. `useSearch` reads `data.error?.message` instead of `data.hint` for 503 responses, matching the API error envelope format. Adds `try/catch` around `res.json()` in `loadApps`, `loadReviews`, `loadTimeseries`, `loadPeriodComparison` to handle non-JSON responses. Prettier formatting on 6 files.

### Keyboard accessibility, ARIA attributes, error boundary

Adds `focus-visible` outline styles on `Btn.vue` (all 6 tones). Adds `@keydown.space` on clickable table rows (`ReviewsTableSection`). Adds `aria-live=polite` on search results container (`SearchSection`). Adds `aria-label` on `PeriodComparisonSection` via GlassCard `$attrs`. Adds `app.config.errorHandler` global error boundary in `main.js`.

---

## open-divine-divinity-rust-bevy: Combat log parallelism, StealthDetection split (771 insertions, 3 files)

### Combat log event-based parallelism

Refactors combat log processing from sequential to event-based parallelism, enabling concurrent execution of combat event handlers. `StealthDetection` split into a separate system for cleaner separation of concerns. `GameAssetData` now used in save/load operations. Major `game.rs` restructuring (1412 insertions/deletions).

---

## wow_constructed_languages: Rounds 77–79 — Zandali, Thalassian, Shath'Yar, sync fixes (318 insertions, 33 files)

### Round 77 — Aln'sharan attestation, Hash'ey update

Adds Aln'sharan as the 5th Aln- attestation. Updates Hash'ey definition. Adds Zatha'tek and Jan'thrazet. Fixes HTML sync gaps.

### Round 78 — Malacrass, Midnight entries, Mantle of Predation

Adds Malacrass to Zandali. Adds missing Midnight entries to Thalassian. Adds Mantle of Predation to Shath'Yar. Fixes HTML-MD sync gaps.

### Round 79 — HTML-MD sync across 7 language families

Fixes HTML-MD sync gaps: earthen italics, nerubian cross-refs, qiraji IPA, ethereal content, mogu theme, eredun nav.

---

## mcp-russia: TOKEN→KLYUCH, licenz→litsenz, docs fixes (138 insertions, 22 files)

### Identifier russification

Unifies `TOKEN` → `KLYUCH` in `settings.py` (2 constants + 2 references). Unifies `licenz` → `litsenz`: Portuguese c → Russian ts for ц (~30 replacements across 12 files). Updates span roskomnadzor (`LicenziyaSvyazi`→`LitsenziyaSvyazi`), minobrnauki, rosprirodnadzor.

### Documentation corrections

Fixes mixed script: `прavo.gov.ru` → `pravo.gov.ru`. Fixes `subyekt` → `subiekt` in politolog.md. Fixes grammar: `юанка` → `юаня`. Fixes `cbrf_sravnit_valyuty` example. Fixes duplicate calls in zhurnalist-stati.md. All 681 tests pass.

---

## My-RU-Coverage: Round 84 — Wikilink and arg russification (134 insertions, 7 files)

### Removal of redundant English names, arg russification

Removes redundant English names from vocabulary. Replaces bare English terms with Cyrillic wikilinks. Russifies `args`/`arg` in `build_network.py`. Network graph data refreshed.

---

## ru-skill: Round 101 — браузер→обозреватель, terminology cleanup (74 insertions, 22 files)

### Terminology normalization

`авторизованных` → `с проверкой подлинности` (3 files). `браузер` → `обозреватель` (4 files: toss-securities, hwp, moex-shares). `интерфейсы API` → `программные интерфейсы` (kleague-results). Bare English terms (JSON/HTML/DOM/Fastify/PM2/JavaScript/npm/curl/base64) wrapped in backticks with «в формате» qualifiers (13 files). YAML SKILL.md: `пакет NAME npm` → `пакет NAME из реестра npm` (3 files). Regression tests updated.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
