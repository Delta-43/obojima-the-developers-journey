# Phase 3 · Step 5 — Testing the API

**Goal:** Add an automated test suite covering the endpoints and business logic you've built so far, running against a real (test) database.

## Why it matters
You're about to build a frontend against this API and, later, plug in an ML model — both are much easier to iterate on if you have a safety net telling you when you've broken something in the backend.

## Concepts to research
- `pytest` fixtures for setting up/tearing down test data
- Testing FastAPI apps with `TestClient`/`httpx`
- Test database strategy: a separate test DB, transactions rolled back per test, or an in-memory/ephemeral instance — pick one and justify it
- The difference between unit tests (pure formula logic) and integration tests (hitting real endpoints + DB)

## Deliverable
- `backend/tests/` with:
  - Unit tests for the brew success formula (Step 3) covering edge cases (perfect match, no match, boundary skill levels)
  - Integration tests for at least: ingredient listing, potion listing with ingredients, registration/login, and a full brew-attempt flow (register → login → brew)
- A documented single command to run the whole suite

## Acceptance criteria
- [ ] The full suite runs green with one command
- [ ] Tests run against a dedicated test database/schema, never your real dev data
- [ ] At least one test deliberately exercises a failure path (bad credentials, invalid ingredient set, unauthenticated request) and asserts the correct error response
- [ ] Running the suite twice in a row gives the same result (no leftover state between runs)

## Hints
- If tests are polluting each other's data, wrap each test in a transaction you roll back afterward — much simpler than manually cleaning up rows.
- This is a good checkpoint to update `Progress.md` — the backend MVP is functionally complete after this step.

---
**Previous:** [04 — Auth & User Accounts](04-auth-and-user-accounts.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [Phase 4 — HTML & CSS Basics](../phase-4-frontend-fundamentals/01-html-css-basics.md)
