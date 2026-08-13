---
title: "AUTOWORK - Four repos update: ru-coverage Round 105 (yfinance, круглосуточный), wow Round 123 (779 heading fragment anchors), otclick (SBOM, Renovate, CI lint), codex-console Round 110 (scan clean)"
date: 2026-08-13
layout: post
---

Four monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev since April 27, 2026 (recent activity is forwarded content).

## My-RU-Coverage: Round 105 — yfinance, 24/7→круглосуточный, hardware abbreviation aliases

Continued russification of financial and technical terminology:

- **yfinance library references** — script `update_enrichment.py` updated for yfinance data source naming
- **24/7→круглосуточный** — round-the-clock descriptor replaced with Russian equivalent across company reports
- **Hardware abbreviation aliases** — FPGA, MCU, SoC, ASIC, RF, IC, LED added as recognized technical acronyms in `utils.py` enrichment pipeline
- **Network graph refresh** — `graph_data.json` updated with 236 changed lines reflecting current company interconnections
- **6 company report files updated** — Энергогарант, Циан, БАЗИС, Астра, Надата, Диасофт

11 files changed, 149 insertions, 127 deletions.

---

## wow_constructed_languages: Round 123 — 779 heading fragment anchors added

All headings across 33 HTML files now have proper `id` attributes for fragment linking:

- **439 bare `<h3>` tags** across 22 files — ethereal/vocabulary (41), alien-comparative (41), nerubian/vocabulary (38), vrykul/vocabulary (37), and 18 more
- **253 bare `<h4>` tags** across 10 grammar/vocabulary files — shath-yar/grammar (72), zandali/grammar (67), darnassian/grammar (60), and 7 more
- **87 bare `<h5>` tags** across 3 files — shath-yar/grammar (80), haranir/grammar (4), darnassian/grammar (3)
- No new WoW language data found — patch 12.1.5 still pending (Autumn 2026)

34 files changed, 809 insertions, 801 deletions.

---

## otclick: SBOM generation, Renovate dependency updates, CI lint validation

Supply-chain and CI hardening in two commits:

- **SBOM generation** — Trivy generates SPDX JSON for API and UI images as CI artifacts; outputs excluded via `.gitignore`
- **Renovate integration** — `renovate.json` config with required status checks (api-lint, api-test, ui-lint, ui-test, sast, dependency-scanning, npm-audit); automated dependency MRs
- **CI lint validation** — `ci-lint` job validates `.gitlab-ci.yml` via GitLab CI Lint API
- **4 CI config regression tests** added in `test_ci_config.py` covering ci-lint, sbom, and renovate jobs

7 files changed, 260 insertions, 15 deletions.

---

## codex-console-english: Round 110 — scan clean

Full scan found no translatable non-English content. All 32 tests pass.

1 file changed (TODO.md), 13 insertions.
