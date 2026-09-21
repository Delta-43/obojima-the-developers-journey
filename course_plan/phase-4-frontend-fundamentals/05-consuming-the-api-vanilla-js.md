# Phase 4 · Step 5 — Consuming the API (Vanilla JS/TS)

**Goal:** Replace the hardcoded data from Steps 3-4 with real data fetched from your Phase 3 FastAPI backend, and wire the "Brew" button to the real brewing endpoint.

## Why it matters
This is the moment the frontend and backend actually connect — the last piece before the product feels like a real, working (if unstyled-by-framework) game.

## Concepts to research
- The `fetch` API: GET/POST requests, handling JSON bodies, and promises/`async`/`await`
- CORS: why your browser will block requests to `localhost:8000` from a page served elsewhere until the backend allows it, and how to configure it in FastAPI
- Handling loading and error states in the UI (what does the page show while waiting, or if the request fails?)
- Storing an auth token client-side (from Phase 3's login endpoint) and attaching it to subsequent requests

## Deliverable
- Ingredient/potion lists now fetched live from `GET /ingredients` and `GET /potions`
- A working login form calling `POST /auth/login`, storing the returned token
- The "Brew" button calling `POST /brew-attempts` with the real selected ingredients and displaying the real success/failure result from the backend

## Acceptance criteria
- [ ] Refreshing the page shows current data from the database, not hardcoded values
- [ ] A failed login shows a real error message from the API, not a silent failure
- [ ] The brew result shown to the user matches what's actually stored in the `brew_attempts` table
- [ ] CORS is configured deliberately (not disabled wholesale in a way you don't understand)

## Hints
- Handle the "unauthenticated" case explicitly in the UI (e.g. hide the brew button until logged in) rather than letting a 401 respond silently.
- This is a great point to update `Progress.md` — you now have a full, working, end-to-end vertical slice: DB → API → UI.

---
**Previous:** [04 — TypeScript Basics](04-typescript-basics.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [Phase 5 — React Fundamentals](../phase-5-frontend-framework/01-react-fundamentals.md)
