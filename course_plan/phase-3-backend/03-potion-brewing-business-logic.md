# Phase 3 · Step 3 — Potion Brewing Business Logic

**Goal:** Implement the actual game mechanic: given a user and a chosen set of ingredients, determine whether the brew succeeds, and persist the attempt.

## Why it matters
This is the heart of the product — and the exact place Phase 6's ML model will later slot in as a smarter replacement for (or supplement to) a hand-written formula.

## Concepts to research
- Designing a first-pass **deterministic formula** for brew success (e.g. based on ingredient rarity matching potion rarity, user skill level, and some randomness) — you are the game designer here, not just the engineer
- Where business logic belongs in a FastAPI app (service/domain layer vs. cramming it into route handlers)
- Using Python's `random` module responsibly (seeding for reproducible tests vs. real randomness in production)
- Writing to multiple related tables in one logical operation (recording the brew attempt, and updating user stats/XP if applicable) inside a transaction

## Deliverable
- A `POST /brew-attempts` endpoint accepting a user, a target potion, and a set of ingredients
- A documented formula (in code comments or `backend/BREWING_FORMULA.md`) for success probability, referencing rarity/level inputs
- The endpoint writes a row to `brew_attempts` recording inputs and outcome
- Basic input validation: reject brews with missing/mismatched ingredients before running the formula

## Acceptance criteria
- [ ] The formula is deterministic given a fixed random seed (so it's testable)
- [ ] Brewing with ingredients that don't match the potion's recipe is rejected with a clear error, not silently processed
- [ ] Every brew attempt (success or failure) is recorded in `brew_attempts` — this table is your future ML training data, so completeness matters
- [ ] You've manually tested both a success and a failure path

## Hints
- Keep the formula simple and explainable for now (e.g. a weighted score compared against a threshold plus randomness) — Phase 6 will replace or augment this with a learned model, so don't over-engineer it.
- Log/record enough input features on each `brew_attempts` row (ingredient rarities used, user level at the time, etc.) — think ahead to what Phase 6 will need as training features.

---
**Previous:** [02 — FastAPI First Endpoints](02-fastapi-first-endpoints.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [04 — Auth & User Accounts](04-auth-and-user-accounts.md)
