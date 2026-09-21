# Phase 3 · Step 4 — Auth & User Accounts

**Goal:** Add real user accounts — registration, login, and authenticated requests — so brew attempts and stats are tied to an actual identity instead of a hardcoded user ID.

## Why it matters
A "user" table with no authentication is just a row nobody owns. This step makes the game multi-player-capable in principle and teaches core web security concepts you'll need in any backend job.

## Concepts to research
- Password hashing (never store plaintext — research `bcrypt`/`argon2` and why fast hashes like plain SHA-256 are unsafe for passwords)
- Session-based auth vs. token-based auth (JWT) — pick one deliberately and know the trade-off you're making
- FastAPI's `Depends` for protecting routes (current-user dependency)
- Basic input validation/sanitization for registration (email/username format, password strength minimums)
- OWASP basics relevant here: broken authentication, sensitive data exposure — know what you're guarding against

## Deliverable
- `POST /auth/register`, `POST /auth/login` endpoints
- A protected route (e.g. `POST /brew-attempts` now requires a valid authenticated user instead of an arbitrary user ID in the body)
- Passwords stored only as salted hashes, never plaintext, verified by inspecting the DB directly

## Acceptance criteria
- [ ] Registering with a duplicate username/email is rejected cleanly
- [ ] Logging in with a wrong password fails without leaking whether the username exists (avoid user enumeration where reasonable)
- [ ] Inspecting the `users` table directly shows only hashed passwords, never plaintext
- [ ] Calling a protected endpoint without a valid token/session returns 401, not a crash
- [ ] Tokens/sessions have some form of expiry

## Hints
- Don't build your own crypto — use a well-vetted library for hashing and, if you go the JWT route, for token creation/verification too.
- This is a good moment to re-read the brew-attempt endpoint from Step 3 and make sure it now trusts the authenticated user's identity, not a client-supplied user ID.

---
**Previous:** [03 — Potion Brewing Business Logic](03-potion-brewing-business-logic.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [05 — Testing the API](05-testing-the-api.md)
