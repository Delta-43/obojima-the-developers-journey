# Phase 7 · Step 1 — Containerization & Deployment

**Goal:** Package the backend, database, and frontend so the whole app can be run with minimal manual setup, and deploy it somewhere publicly reachable.

## Why it matters
A project that only runs on your machine isn't finished, and deployment surfaces real-world concerns (config, secrets, environment parity) you haven't had to face yet.

## Concepts to research
- Docker basics: images, containers, a `Dockerfile` per service, and `docker-compose` for running backend + DB + frontend together
- Environment parity: making sure "works on my machine" becomes "works in the container" (dependency pinning matters here)
- Where to deploy for free/cheap for a portfolio project (a PaaS for the backend+DB, static hosting for the frontend) — pick based on your budget and note your choice and reasoning
- Basic production concerns: not running with debug mode on, not exposing stack traces to users, environment-based secrets (never committed)

## Deliverable
- `Dockerfile`s for backend and frontend, and a `docker-compose.yml` that runs backend + PostgreSQL + frontend together locally with one command
- The app deployed somewhere publicly accessible (even a modest free tier is fine)
- A root `DEPLOYMENT.md` documenting the deployed URL, how to redeploy, and how to run everything locally via Docker

## Acceptance criteria
- [ ] `docker-compose up` (or equivalent) brings up a fully working stack from a clean checkout, including running migrations and seeding data if needed
- [ ] The deployed version is reachable by URL and its core flow (login → browse ingredients → brew a potion) works end to end
- [ ] No secrets are committed to the repo; the deployed environment gets its config via environment variables/secrets manager
- [ ] Debug/verbose error output is disabled in the deployed environment

## Hints
- Get the Docker Compose local setup solid before worrying about a public deployment target — most of the learning value is in containerizing correctly.

---
**Previous:** [Phase 6 — Serving the Model from the API](../phase-6-machine-learning/04-serving-the-model-from-the-api.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [02 — Retrospective & Next Steps](02-retrospective-and-next-steps.md)
