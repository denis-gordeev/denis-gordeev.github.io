---
title: "AUTOWORK - WoW Rounds 33-36: Shath'Yar noun incorporation, nVq root, Darnassian /ks/ phoneme and frozen reduplication, MCP-Russia hybrid suffix russification, RU-Coverage rounds 64-65, ru-skill rounds 81-82 deep russification, codex-console 78 translation artifact fixes"
date: 2026-07-07
layout: post
---

Five repositories see new commits on July 7: **[wow_constructed_languages](https://github.com/denis-gordeev/wow_constructed_languages)** ships Rounds 33-36 with Shath'Yar Investigations 13-16 (noun incorporation, refined auxiliaries, nVq root, qam polysemy) and Darnassian Investigation 17 (/ks/ phoneme and frozen reduplication), **[mcp-russia](https://github.com/denis-gordeev/mcp-russia)** russifies hybrid class suffixes and documentation, **[My-RU-Coverage](https://github.com/denis-gordeev/My-RU-Coverage)** completes rounds 64-65 with terminology and typo cleanup, **[ru-skill](https://github.com/denis-gordeev/ru-skill)** reaches rounds 81-82 with deep russification of calques and borrowings, and **[codex-console-english](https://github.com/denis-gordeev/codex-console-english)** fixes 78 Chinese-English translation artifacts and verifies round 68.

## wow_constructed_languages: Rounds 33-36 — Shath'Yar Investigations 13-16, Darnassian /ks/ and reduplication

Four commits (1154 insertions, 64 deletions, 34 files):

### Round 33: Shath'Yar Investigations 13-14 — noun incorporation, refined auxiliaries

- **Investigation 13: Object incorporation** — *erh'ongg* analyzed as verb *erh* "choke" + incorporated noun *ongg*; first candidate for Shath'Yar object incorporation, a typologically significant polysynthetic feature; Low–Moderate confidence
- **Investigation 14: Refined auxiliary system** — four-way future system proposed: *qi'* synthetic prefix (default), *wgah* analytic auxiliary (complex constructions), *agth* obligative, *gag* emphatic; typological parallel with French synthetic vs. analytic future (*je ferai* vs. *je vais faire*); Investigation 12 findings integrated

### Round 34: Xaxas reduplication, Aethenar, nerubian bakh/bkah root

- **Xaxas** added to Darnassian vocabulary — potential frozen reduplication candidate (*Xa-Xas*)
- **Aethenar** added — second *-thenar* attestation after *Mathiel'thenar*
- **Nerubian bakh/bkah root** observation: *bakh* (in *Shabtir bakh sokhen*) and *bkah* (in *Bkah'za*) may share a root with metathesis; Very Low confidence

### Round 35: Darnassian Investigation 17 — /ks/ phoneme, frozen reduplication

- **/ks/ phoneme**: Darnassian *Xaxas* and *Althalaxx* contain /ks/ — not a single phoneme but a cluster consistent with Darnassian phonotactics; *Althalaxx* = *Althal* + *-axx* suffix or frozen compound
- **Frozen reduplication**: *Xaxas* likely *Xa-Xas* (frozen echo-word) rather than productive reduplication; Pattern 12 (name formation) updated; systematic search found no productive reduplication in Darnassian

### Round 36: Shath'Yar Investigations 15-16, Hara'ni-Zandali comparison, -mara upgrade

- **Investigation 15: nVq root** — *nuq* (2nd-person propositional negation) and *noq* (verb "see") may share a Proto-Shath'Yar *nVq* root; if correct, *nVq* → *nuq* via grammaticalization; Low confidence, requires new data
- **Investigation 16: qam polysemy** — three distinct *qam* morphemes: *qam*₁ negation (high confidence), *qam*₂ fused negative future in *wgah qam* (Low–Moderate), *qam*₃ potential copula in *Fssh qam* (Very Low); polysemy likely reflects homophonous convergence rather than single polysemous morpheme
- **Hara'ni-Zandali morphological comparison**: systematic table comparing compounding, suffixation, and noun-class systems across the two Troll-family languages
- ***-mara*** confidence upgraded to Moderate (additional attestation evidence)

Investigation count: 16 total (Shath'Yar 16, Darnassian 17).

---

## mcp-russia: Hybrid class suffix russification, documentation fixes

Two commits (194 insertions, 91 deletions, 27 files):

- **Class suffix russification**: PartiaInfo → InformatsiyaPartii, KomitetInfo → InformatsiyaKomiteta, ZasedanieInfo → InformatsiyaZasedaniya, SputnikMonitoring → SputnikovyyMonitoring
- **Field/parameter russification**: EtapPlana.instrument → imya_instrumenta, discovery.py instrument → obiekt_instrumenta, deloproizvodstvo/server.py prompts → промпты
- **Documentation updates**: discovery → обнаружение, client → клиент, orchestration → оркестрация, retry → повторные попытки; Росавдит → Счётная палата (3 occurrences); tool counts corrected (203→212)
- **Stale link fixes**: Makefile registry→reyestr, README McpRussiaError→OshibkaMcpRussia, CONTRIBUTING auto-registry→автообнаружение
- ruff check passed, ruff format passed, pytest 547 passed

---

## My-RU-Coverage: Rounds 64-65 — terminology cleanup and typo fixes

Two commits (263 insertions, 224 deletions, 23 files):

### Round 64: Content and terminology alignment

| Change | Scope |
|--------|-------|
| контент → содержимое | Generic borrowing |
| дженерики → препараты-аналоги | Medical terminology |
| Enrichment JSON sync | Data consistency |
| Theme counter fix | Metadata |

### Round 65: Typos, Latin in comments, narrow aliases

| Change | Scope |
|--------|-------|
| викалинк → викилинк | Typo (3 occurrences) |
| Фокус → Акцент | Borrowing |
| Маппинг → Сопоставление | Borrowing |
| [[wikilinks]] → [[викилинки]] | Latin in docstrings |
| SGA/CAPEX/FCF Russian annotations | Financial acronyms |
| офшорная → офшорная ветроэнергетика | Narrowed unsafe alias |

---

## ru-skill: Rounds 81-82 — hybrid unification and deep calque replacement

Two commits (509 insertions, 264 deletions, ~58 files):

### Round 81: Hybrid term unification ENGLISH-русское → русское ENGLISH

~130 replacements across ~30 files, extending round 80's pattern:

| Before | After |
|--------|-------|
| delivery-tracking | отслеживание-доставки |
| endpoint | конечная точка |
| adapter | модуль-посредник |
| validator | модуль проверки |
| parsing | разбор |
| browser-based | в обозревателе |
| env → переменные окружения | Abbreviation expansion |
| CI → система непрерывной интеграции | Abbreviation expansion |
| user-agent → пользовательский агент | Calque replacement |

### Round 82: Deep russification of calques and borrowings

~70 replacements across ~28 files:

| Before | After |
|--------|-------|
| прокси | посредник |
| кэш | буфер |
| аутентификация | проверка подлинности |
| хост | имя узла |
| аккаунт | учётная запись |
| логин | вход |

---

## codex-console-english: 78 Chinese-English artifact fixes, round 68

Two commits (115 insertions, 92 deletions, 27 files):

- **Fix 78 Chinese-English translation artifacts** across source, templates, JS, and tests — systematic removal of residual Chinese characters from comments, strings, and variable names in 26 files
- **Round 68**: all tracked files verified English-only; 32 tests pass

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
