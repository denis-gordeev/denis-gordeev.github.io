---
title: "AUTOWORK - otclick: Thread-safe cache, apps pagination, standardized error envelope, OpenAPI error documentation — API v0.19.0→v0.20.0"
date: 2026-07-19
layout: post
---

One repository sees new commits on July 18: **[otclick](https://github.com/denis-gordeev/otclick)** ships two commits that add thread-safe caching, apps endpoint pagination, a standardized error envelope, and OpenAPI error documentation — bumping the API from v0.19.0 to v0.20.0.

## otclick: Two commits — thread-safe cache, error envelope, OpenAPI documentation (310 insertions, 8 files)

### Thread-safe InProcessCache, apps pagination, standardized error envelope (0829547)

Adds `threading.Lock` to `_InProcessCache` for multi-worker safety — all `_store` mutations (get, set, close) are now lock-protected. Introduces `limit`/`offset` pagination on `/api/apps` with `total` count, using `COUNT(DISTINCT)` + `LIMIT/OFFSET` SQL. Standardizes all error responses to a `{"error": {"code": "...", "message": "..."}}` envelope via new `ErrorDetail`, `ErrorResponse` models and `_error_response()` helper — replacing the previous ad-hoc JSON structures on `/api/reviews/search` (503) and `/api/reviews/breakdown/{field}` (422). Bumps API version to 0.19.0. 9 new tests cover thread safety, pagination, and error envelope structure. 228 insertions across 4 files.

### Document structured API errors in OpenAPI (cbf675e)

Adds `ErrorResponse` to OpenAPI `responses` for all custom non-2xx paths: `/api/reviews/search` documents 503, `/api/reviews/breakdown/{field}` documents 422. A regression test against `/openapi.json` verifies the `$ref` to `#/components/schemas/ErrorResponse`. `dwh/tests/conftest.py` now adds `dwh/src` to `sys.path` automatically, so `pytest` works without manual `PYTHONPATH=src`. API version and `dwh/pyproject.toml` synchronized at 0.20.0. Root `.gitignore` now ignores `/node_modules/`. 82 insertions across 7 files.

---

Explore all repositories at [`github.com/denis-gordeev`](https://github.com/denis-gordeev).
Shorter updates: [`t.me/nlp_party`](https://t.me/nlp_party).
