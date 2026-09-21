# Phase 0 · Step 2 — Git & Project Structure

**Goal:** Establish the repository layout that will host every later phase's code, and a Git workflow you'll actually stick to.

## Why it matters
You're building a monorepo with several independent pieces (DB migrations, ETL scripts, backend API, frontend app, ML notebooks/scripts). Deciding folder boundaries now avoids painful reshuffling later.

## Concepts to research
- Monorepo layout conventions (top-level folders per concern vs. per language)
- Git branching basics: feature branches, commits as checkpoints, meaningful commit messages
- Semantic-ish commit message styles (doesn't need to be strict Conventional Commits, but be consistent)
- Environment variables and `.env` files for secrets/config (and why they're gitignored)

## Deliverable
Create the top-level skeleton (empty folders with a `.gitkeep` or a placeholder `README.md` are fine — you'll fill them in as each phase arrives):
```
backend/         # FastAPI app (Phase 3+)
database/        # schema/migrations (Phase 1+)
etl/             # extraction/load scripts (Phase 2+)
frontend/        # vanilla site, later React app (Phase 4+)
ml/              # training scripts/notebooks (Phase 6+)
course_plan/     # (already exists)
raw_assets/      # (already exists)
```
Plus a root `.env.example` documenting expected environment variables (no real secrets).

## Acceptance criteria
- [ ] Repo has the folder skeleton above, each committed with at least a placeholder
- [ ] A `.env.example` exists; `.env` itself is gitignored
- [ ] You've made at least 2-3 real commits with descriptive messages (not "wip")
- [ ] You can explain, in one sentence each, what will live in every top-level folder

## Hints
- You don't need to commit to an exact structure forever — but avoid restructuring every phase; that churn is expensive.
- If you're unsure whether something is a "secret", treat it as one.

---
**Previous:** [01 — Tooling & Environment Setup](01-tooling-and-environment-setup.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [03 — Python Refresher for Engineers](03-python-refresher-for-engineers.md)
