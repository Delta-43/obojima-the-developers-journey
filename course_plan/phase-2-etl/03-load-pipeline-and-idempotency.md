# Phase 2 · Step 3 — Load Pipeline & Idempotency

**Goal:** Write the "Load" half of the pipeline: take the structured records from Step 2 and safely persist them into PostgreSQL, including the many-to-many potion↔ingredient relationships.

## Why it matters
This is the step that actually populates the database your backend (Phase 3) will serve from. Getting the relationships and re-run safety right here saves you from corrupt or duplicated data down the line.

## Concepts to research
- A Python DB driver/toolkit: `psycopg` directly, or an ORM (SQLAlchemy) — worth deciding now since Phase 3's FastAPI backend will likely reuse the same DB layer
- Upsert patterns (`INSERT ... ON CONFLICT`) vs. "check then insert" (and why the latter has race conditions, even if it doesn't matter at your current scale)
- Transactions: wrapping a whole load run so a failure partway through doesn't leave the DB half-populated
- Loading image assets: decide now whether images live as file paths referenced in the DB, or get copied/renamed into a `static/`-style folder your future backend will serve

## Deliverable
- `etl/load.py` that takes parsed records and writes them into `ingredients`, `potions`, and `potion_ingredients`
- A single entry-point script/command (e.g. `python -m etl.run`) that does extract → transform → load end to end
- Images copied/organized into a location your backend will later serve, with DB rows referencing them correctly

## Acceptance criteria
- [ ] Running the full pipeline twice in a row does not create duplicate ingredients/potions
- [ ] All ~130 ingredients and the full potion list end up in the database (or you have a documented, deliberate reason for any exclusions)
- [ ] Every potion row has correctly linked ingredient rows via the junction table
- [ ] A failed run (simulate one, e.g. by interrupting it or feeding bad data) doesn't leave partial/corrupt data — the transaction rolls back
- [ ] You can query the DB and get back an ingredient's image path/reference

## Hints
- Wrap the whole load in one DB transaction if your data volume allows it (it does, at this scale) — simplest way to get atomicity for free.
- This is a natural point to update `Progress.md` — the DB now has real product data in it, which is a genuine milestone.

---
**Previous:** [02 — Parsing the Raw Sourcebook Data](02-parsing-raw-source-data.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [Phase 3 — HTTP & REST API Concepts](../phase-3-backend/01-http-rest-api-concepts.md)
