---
title: "AUTOWORK - Six repos update: otclick fail-closed deployment profiles (API v0.59.0, 493→508 tests), ru-skill Round 130 (CLI пояснения, английские h1/метки в tg/, Fastify/station-list кавычки), mcp-russia auth metadata sync + docs refresh (27 modules), My-RU-Coverage Round 109 (путь_джсон, построить_хтмл, 5 падежей викилинков), wow_constructed_languages Rounds 129–130 (HTML quality fixes, &asymp;/&sect; entities), codex-console-english Rounds 114–115 (scan clean)"
date: 2026-08-19
layout: post
---

Six monitored repositories have new commits since the previous round. Telegram channel t.me/nlp_party has no new original posts by Denis Gordeev (recent activity is forwarded content). open-divine-divinity-rust-bevy has no new commits.

## otclick: fail-closed deployment profiles, API v0.59.0 (493→508 tests)

Runtime security hardening — deployed APIs now refuse to start with unsafe configuration:

- **APP_ENV profiles**: `development|test|staging|production` — staging and production validated before DB, Redis or HTTP middleware init
- **Fail-closed checks**: deployed profiles require HTTPS CORS_ORIGINS (no credentials/path/query/fragment/loopback), API_KEYS ≥32 chars, valid IP TRUSTED_PROXIES, enabled rate limit with Redis storage
- **Backward-compatible**: local profiles keep convenient defaults
- **docker-compose.yml + .env.example** document runtime profiles; proxy header warning corrected
- **API v0.59.0**, 15 new parameterized pytest regressions (493→508 tests, coverage 100%)

9 files changed, 217 insertions, 7 deletions.

---

## ru-skill: Round 130 — CLI пояснения, английские h1/метки в tg/, Fastify/station-list кавычки

Periodic audit found and fixed remaining English/jargon issues:

- **CLI без пояснения → (интерфейсы командной строки)**: 6 files — `1Password CLI`, `Bitwarden CLI` in docs/setup.md, docs/security-and-secrets.md, k-skill-setup/SKILL.md, srt-booking/SKILL.md, ktx-booking/SKILL.md, seoul-subway-arrival/SKILL.md
- **Английские h1/метки в tg/*/README.md**: 4 files — added Russian subtitle `(зеркальный канал)`, `Repo:` → `Репозиторий:`, `pending` → `ожидается`
- **packages/k-skill-proxy/README.md**: `# k-skill-proxy` → `# Сервер-посредник k-skill-proxy`, `Fastify` wrapped in backticks
- **docs/features/fine-dust-location.md**: `station-list` wrapped in backticks
- All 23 key tracked jargon terms confirmed not reverted in user-facing documentation

16 files changed, 52 insertions, 25 deletions.

---

## mcp-russia: authorization metadata sync, docs refresh (24→27 modules)

Metadata and documentation synchronized with actual tool behavior:

- **operatsii_trebuyut_avtorizatsii synced** with _zametka_ob_avtorizatsii() usage: Закупки added plany_zakupok, poisk_rnp; Госдума added info_deputata with auth note
- **Module counter fixed**: smart-tools.md «24 активных модуля» → «27 модулей»
- **sovfed tool count fixed**: «6 инструментов» → «7 инструментов»; added info_senatora, poimennoe_golosovanie
- **Removed stale labels**: «планируемый инструмент» for poimennoe_golosovanie, «планируемый модуль» for kaznacheistvo
- **Migration wording removed** in zhurnalist-stati.md: «полностью ориентирован на российский контекст» → «работает с российскими государственными данными и API»

10 files changed, 40 insertions, 16 deletions.

---

## My-RU-Coverage: Round 109 — путь_джсон, построить_хтмл, 5 падежей викилинков

Mixed Russian-English identifiers eliminated and wikilink cases corrected:

- **путь_json → путь_джсон** (8 occurrences, 2 scripts): consistent with --джсон convention from Round 100
- **построить_html → построить_хтмл** (1 declaration + 1 call): last mixed identifier in build_network.py
- **текст_html → текст_хтмл, путь_html → путь_хтмл** (4 occurrences): variable names unified
- **HTML-визуализацию → ХТМЛ-визуализацию** (1 docstring): anglicism in documentation
- **Wikilink grammatical case fixes** (5 occurrences, 4 reports): `[[Линукс]]` → `[[Линукс|Линукса]]`, `[[Альт Линукс]]` → `[[Альт Линукс|Альт Линуксом]]`, `[[Русал]]` → `[[Русал|Русала]]`, `[[Сбер]]` → `[[Сбер|Сбера]]`, `[[Компас-3D]]` → `[[Компас-3D|Компасом-3D]]`
- Full russification audit: all 43 reports, 13 scripts checked — no remaining anglicisms needing replacement
- Full wikilink case audit complete — no remaining errors

9 files changed, 161 insertions, 144 deletions.

---

## wow_constructed_languages: Rounds 129–130 — HTML quality fixes, entity normalization

Two rounds of HTML cleanup across the 80+ file corpus:

**Round 129:**
- 6 `&approx;` → `&asymp;` for consistency (earthen/vocabulary.html 2, ethereal/grammar.html 1, ethereal/vocabulary.html 3)
- Non-ASCII id attribute fix: `correspondence-5-palatalization-s-&gt-ʃ-_i` → `correspondence5-palatalization-s-gt-sh-i`
- Darnassian grammar heading mismatch: 3 `<h4>` headings converted to `<p><strong>` to match .md source; missing Assessment `<h4>` added
- Missing text in ethereal/vocabulary.html Domanaar tree restored

**Round 130:**
- 2 missing `<h4>Evidence Table</h4>` headings in darnassian/grammar.html (Investigations 10–11)
- 34 bare `§` → `&sect;` across 6 HTML files (haranir, ethereal, nerubian)

10 files changed, 63 insertions, 52 deletions.

---

## codex-console-english: Rounds 114–115 — scan clean

Two consecutive clean scans:
- **Round 114**: full scan confirms fully English; non-ASCII limited to legitimate exceptions (UI emojis, `Türkiye`)
- **Round 115**: no non-English content found; all 32 tests pass

1 file changed (TODO.md updates).
