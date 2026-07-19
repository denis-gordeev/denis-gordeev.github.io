---
title: "AUTOWORK - otclick: thread-safe cache, apps pagination, standardized error envelope (v0.19.0), OpenAPI error documentation (v0.20.0)"
date: 2026-07-19
layout: post
---

**[otclick](https://github.com/denis-gordeev/otclick)** lands two commits advancing API reliability and documentation: a thread-safe cache, paginated `/api/apps`, and a standardized error envelope in v0.19.0; followed by OpenAPI error response documentation and test bootstrap improvements in v0.20.0. All other monitored repos show no new commits since July 18.

## otclick: API v0.19.0 — Thread-safe cache, apps pagination, error envelope (228 insertions, 4 files)

### Thread-safe InProcessCache

Adds `threading.Lock` to `_InProcessCache`, wrapping `get()`, `set()`, and `close()` with lock acquisition to prevent data races under multi-worker deployments. Two new tests verify concurrent read/write safety.

### Apps endpoint pagination

The `/api/apps` endpoint now accepts `limit` (1–500, default 100) and `offset` (≥0, default 0) query parameters and returns `total`, `limit`, `offset`, and `items` in the response. Uses `psycopg.rows.dict_row` for cleaner result handling. Falls back to `total=0` when the table does not exist.

### Standardized error envelope

Introduces `ErrorDetail` and `ErrorResponse` Pydantic models and a `_error_response()` helper. All non-2xx responses (503 on `/api/reviews/search`, 422 on `/api/reviews/breakdown/{field}`) now return a consistent `{error: {code, message}}` envelope with machine-readable error codes (`es_not_configured`, `es_unavailable`, `unknown_breakdown_field`). Seven new tests cover the envelope structure and apps pagination.

---

## otclick: API v0.20.0 — OpenAPI error documentation, test bootstrap (82 insertions, 7 files)

### OpenAPI structured error responses

Adds `_ERROR_RESPONSE_DESCRIPTIONS` and `_error_responses()` helper to wire `ErrorResponse` into OpenAPI `responses` for specific status codes. `/api/reviews/search` now documents its 503 response; `/api/reviews/breakdown/{field}` documents its 422 response. A new test asserts that `/openapi.json` includes the `ErrorResponse` schema and that the correct `$ref` is wired into both endpoints.

### pytest conftest bootstrap

`dwh/tests/conftest.py` now inserts `dwh/src` into `sys.path` automatically, so API tests run with plain `pytest` without manual `PYTHONPATH=src`. Requires Python 3.11+ as declared in `pyproject.toml`.

### Version synchronization

API version in `api.py` and package version in `dwh/pyproject.toml` are both aligned at `0.20.0` (previously `0.18.0` in api.py and `0.17.0` in pyproject.toml diverged after the v0.19.0 bump).

### .gitignore

Adds `/node_modules/` to the root `.gitignore` to prevent local npm artifacts from cluttering `git status`.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
