# Phase 3 · Step 1 — HTTP & REST API Concepts

**Goal:** Understand what an API actually is before building one: HTTP methods, status codes, request/response bodies, and REST resource conventions.

## Why it matters
Everything from here to the end of the project talks to your data through an API. If the conceptual model (resources, verbs, statelessness) isn't clear, FastAPI's abstractions will feel arbitrary instead of logical.

## Concepts to research
- HTTP methods and their conventional meaning: `GET`, `POST`, `PUT`/`PATCH`, `DELETE`
- Status codes: 2xx success, 4xx client error, 5xx server error — and which ones matter for your use cases (200, 201, 400, 404, 422, 500 at minimum)
- REST resource naming conventions (`/ingredients`, `/ingredients/{id}`, `/users/{id}/brew-attempts`)
- Request/response bodies as JSON, and content negotiation basics
- Statelessness: why each request must carry everything the server needs (ties into auth in Step 4)

## Deliverable
No code — a short `backend/API_DESIGN.md` sketching the endpoints you'll need for the MVP, e.g.:
- `GET /ingredients`, `GET /ingredients/{id}`
- `GET /potions`, `GET /potions/{id}`
- `POST /brew-attempts` (the core game action: attempt to brew a potion)
- `GET /users/{id}`, endpoints for user stats
Document the method, path, expected request body (if any), and expected response shape for each.

## Acceptance criteria
- [ ] Every endpoint has a clear resource noun and an appropriate HTTP verb (no `GET /getAllIngredients`-style RPC naming)
- [ ] You've decided what status code each endpoint returns on success and on failure
- [ ] You can explain, in your own words, why `POST /brew-attempts` shouldn't be a `GET`

## Hints
- Keep the endpoint list to what the MVP game actually needs — resist designing a full CRUD admin API for every table right now.

---
**Previous:** [Phase 2 — Load Pipeline & Idempotency](../phase-2-etl/03-load-pipeline-and-idempotency.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [02 — FastAPI First Endpoints](02-fastapi-first-endpoints.md)
