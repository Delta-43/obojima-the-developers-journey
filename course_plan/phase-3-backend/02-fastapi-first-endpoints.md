# Phase 3 · Step 2 — FastAPI First Endpoints

**Goal:** Stand up a running FastAPI application with read-only endpoints for ingredients and potions, backed by the real database from Phase 1/2.

## Why it matters
This is the first time the whole stack — DB → backend → response — connects end to end. Everything else in the backend phase builds on this skeleton.

## Concepts to research
- FastAPI project structure (routers, dependency injection via `Depends`)
- Pydantic models for request/response validation — and how they differ from your DB models
- Connecting FastAPI to PostgreSQL (SQLAlchemy session management, or your chosen DB layer from Phase 2)
- Automatic docs (`/docs`) and why they come "for free" with typed FastAPI routes
- Environment-based configuration (dev vs. prod DB URLs) via `.env`

## Deliverable
- `backend/` FastAPI app with, at minimum:
  - `GET /ingredients` and `GET /ingredients/{id}`
  - `GET /potions` and `GET /potions/{id}` (including their required ingredients)
- Pydantic response models matching your API design doc from Step 1
- The app runnable locally with a single documented command

## Acceptance criteria
- [ ] `GET /ingredients` returns real data loaded by your Phase 2 pipeline, as JSON
- [ ] `GET /potions/{id}` includes the linked ingredients (proving your junction table + query work end to end)
- [ ] Requesting a non-existent ID returns a proper 404, not a 500
- [ ] `/docs` renders and accurately reflects your response shapes
- [ ] DB credentials come from environment config, not hardcoded strings

## Hints
- Separate your Pydantic "API schema" models from your DB/ORM models even though it feels redundant at first — it pays off once they need to diverge (e.g. hiding internal fields).
- If you used raw `psycopg` in Phase 2 and it's getting cumbersome, this is a natural point to introduce SQLAlchemy — just be deliberate about the switch.

---
**Previous:** [01 — HTTP & REST API Concepts](01-http-rest-api-concepts.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [03 — Potion Brewing Business Logic](03-potion-brewing-business-logic.md)
