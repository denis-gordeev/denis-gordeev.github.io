---
title: "AUTOWORK - WoW Rounds 37-40: Nerubian -kan suffix, Vrykul/Orcish investigations, Nazja/Zandali/Taur-ahe/Kalimag new analyses, Divine Divinity combat HUD + NPC voices, MCP-Russia FSSP tool + docs russification, RU-Coverage rounds 66-68 CLI flags and terminology, ru-skill round 83 token→маркер"
date: 2026-07-08
layout: post
---

Seven repositories see new commits on July 8: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Rounds 37-40 with Nerubian suffix analysis, Ethereal gender system, Vrykul/Orcish investigations, and first investigations for four under-analyzed languages (Nazja, Zandali, Taur-ahe, Kalimag), **[open-divine-divinity-rust-bevy](https://github.com/denis-gordeev/open-divine-divinity-rust-bevy)** adds combat intensity HUD and NPC voice variation (874 tests), **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** registers FSSP spisok_regionov and russifies test variables and documentation, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** completes rounds 66-68 with CLI-flag russification and terminology cleanup, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches round 83 replacing токен→маркер and unifying hybrid terms, **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** confirms rounds 69-71 with repo fully English, and **[birdclef_2026](https://github.com/denis-gordeev/birdclef_2026)** has no actionable work.

## wow_constructed_languages: Rounds 37-40 — Nerubian, Ethereal, Vrykul, Orcish, and four under-analyzed languages

Three commits (1886 insertions, 56 deletions, 49 files):

### Round 37: Nerubian -kan/-akan suffix, Ethereal Domanaar, Qiraji/Sethrak/Vulpera

- **Nerubian -kan/-akan suffix**: *-kan* agentive and *-akan* plural agentive identified; *-na* particle analyzed as sentence-final marker
- **Ethereal Domanaar gender system**: diachronic naming patterns with gendered endings; Consort/Domina distinction parallels
- **Qiraji**: new grammatical patterns added to description and grammar
- **Sethrak**: new grammatical patterns documented
- **Vulpera**: expanded grammar analysis
- **Darnassian**: HTML sync fix

### Round 39: Vrykul Investigations 2-3, Orcish Grom- root analyses

- **Vrykul Investigation 2: uul/buul independent derivation** — *uul* and *buul* analyzed as independently derived rather than morphologically related
- **Vrykul Investigation 3: Mj- phonological onset** — *Mj-* pattern in vrykul names (e.g., *Mjordin*, *Mjolnir*) as phonological onset cluster
- **Orcish Grom- root**: *Grom-* analyzed as potential root morpheme; *-mar*, *-rand*, *-grim* suffix analyses added
- 14 new vocabulary entries for Vrykul

### Round 40: First investigations for four under-analyzed languages

- **Nazja** (4 new investigations, previously had 0):
  - Investigation 1: *-ess/-esh* feminine/tribal name-final pattern (6 names)
  - Investigation 2: *thero/thera* element and Darnassian cognate
  - Investigation 3: Sibilant-initial name dominance (~40% of names)
  - Investigation 4: *Be'/Fara* initial elements as imperative markers
- **Zandali Investigation 9**: *-watha/Watha'* bidirectional distribution and verb-noun connection; grammaticalization chain hypothesis: 'cleanse' → 'cleansed place' → 'settlement'
- **Taur-ahe Investigation 5**: *-sha/-she* celestial morpheme (*An'she*, *Mu'she*, *Mashan'she*); Moderate confidence — highest-confidence Taur-ahe morpheme hypothesis
- **Kalimag Investigation 6**: Cross-dialect lexical correspondence (*bromo*, *Reth* across Ignan/Aquan)

---

## open-divine-divinity-rust-bevy: Combat intensity HUD and NPC voice variation

Two commits (749 insertions, 57 deletions, 10 files, 848→874 tests):

### Combat music intensity scaling and NPC voice-over

- **Combat music intensity**: volume scales 70-100%, speed 1.0-1.15x based on enemy count and boss phase; *CombatMusicIntensity* resource tracks state
- **NPC voice-over**: *NpcVoiceGreeting/Response/Farewell* sounds triggered on dialog open/advance/close; procedural placeholder tones as fallback
- 13 new tests (848→861)

### Combat intensity HUD indicator and NPC voice variation

- **CombatIntensityHud**: visual bar with tier labels (CALM/HEATED/INTENSE/EXTREME); color-coded fill (purple→yellow→orange→red); boss phase info or enemy count display
- **NpcVoiceProfile**: pitch_multiplier and speed_multiplier per NPC; *for_npc_name()* maps 15 NPCs to unique voice identities; *PendingSound* replaces Vec<GameSound>; *try_play_sound_with_speed()* for per-NPC voice speed
- 13 new tests (861→874)

---

## mcp-russia: FSSP spisok_regionov, test and documentation russification

Two commits (297 insertions, 161 deletions, 53 files):

- **FSSP spisok_regionov** registered (9→10 tools)
- **Test variable russification**: *prompt_names* → *imena_promtov* (17 files), *mock_* → *maket_*, *legacy_mcp* → *prezhnyaya_mcp*, *raw* → *syryye_dannye*, *codes* → *kody*, *reg* → *reyestr*, *names* → *imena*, *messages* → *soobshcheniya*
- **Documentation russification**: namespace→пространство имён, legacy→устаревший, timeout→таймаут, async→асинхронный, env vars→переменные окружения, workflow→рабочий процесс, production→рабочие, runtime→среда выполнения
- **Schema fix**: ДЕЙСТВУЮЩАЯ/ЛИКВИДИРОВАНА in rosapi schemas
- **CONTRIBUTING.md**: English commit examples → Russian

---

## My-RU-Coverage: Rounds 66-68 — CLI flags, terminology, and anglicism cleanup

Three commits (735 insertions, 592 deletions, ~93 files):

### Round 66: Corporate terminology and CLI flag russification

| Change | Scope |
|--------|-------|
| корпоративные клиенты → клиенты из числа предприятий | Borrowing |
| локальная_компания → российская_компания | Terminology |
| top → лимит | CLI flag |
| сниппет → фрагмент | Anglicism |
| голубые фишки → крупнейшие акции | Calque |
| инвестпрезентация → инвестиционная презентация | Abbreviation expansion |

### Round 67: CLI flags and documentation

- **21 CLI flags russified**: --dry-run→--пробный-запуск, --sector→--сектор, --index→--индекс, --date→--дата, --data→--данные, --list→--список, etc.
- **CLAUDE.md**: wikilink conventions russified
- **Reports**: голубых фишек→крупнейших акций, витрины→площадки, premium-class→премиальные

### Round 68: Reverse terminology fixes and grammar

| Change | Scope |
|--------|-------|
| клиенты из числа предприятий → корпоративные клиенты (22) | Reverse optimization |
| совокупность услуг → комплекс услуг (10) | Collocation |
| застройщицкая → компания-застройщик (3) | Terminology |
| --list → --список | CLI flag fix |
| рендер → формирование | Anglicism |

---

## ru-skill: Round 83 — token→маркер, historical section russification

One commit (119 insertions, 62 deletions, 20 files):

- **токен → маркер/маркер доступа** in interface documentation (9 replacements in 7 files)
- **прокси → посредник** in historical sections of TODO.md, roadmap.md, README.md (18 occurrences)
- **эндпоинт → конечная точка** in historical sections (4 occurrences)
- **Hybrid term unification**: ENGLISH-русское → русское ENGLISH (14 replacements in 11 files)
- Russian annotations added for REST API, OIDC, User-Agent

---

## codex-console-english: Rounds 69-71 — confirmed fully English

Three commits (TODO updates only):
- Rounds 69-71 all confirm no new non-English content; repo verified fully English.

## birdclef_2026: No actionable work

Two commits (TODO updates only):
- Competition closed; no new actionable work.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
