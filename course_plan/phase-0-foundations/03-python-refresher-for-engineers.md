# Phase 0 · Step 3 — Python Refresher for Engineers

**Goal:** Bring your existing Python skills up to the idioms you'll lean on for backend/ETL/ML work: type hints, packaging, virtual environments in practice, and testing basics.

## Why it matters
You already know Python syntax from prior experience — this step is about the *engineering* habits (typing, structure, testing) that separate scripts from services, not the language basics.

## Concepts to research
- Type hints (`typing` module) and why FastAPI/Pydantic lean on them heavily
- `dataclasses` vs. plain classes vs. Pydantic models (you'll meet Pydantic properly in Phase 3)
- Writing and running a unit test with `pytest`
- Formatting/linting tools (`black`, `ruff`) and why consistent style matters in a solo *and* public project
- Reading a `requirements.txt` / `pyproject.toml` and pinning versions

## Deliverable
A tiny throwaway script (e.g. `scratch/warmup.py`, later deletable) that:
- Defines a typed function or two with type hints
- Has at least one `pytest` test verifying its behavior
- Passes a linter/formatter with no errors

## Acceptance criteria
- [ ] `pytest` runs and passes in your environment
- [ ] Your formatter/linter of choice runs clean on the scratch script
- [ ] You can explain what a type hint does *and* does not enforce at runtime in plain Python

## Hints
- This step is intentionally small — the real Python growth happens across Phases 2, 3, and 6. Don't over-invest here.
- If `pytest` or type hints are already second nature to you, skim this step and move on quickly.

---
**Previous:** [02 — Git & Project Structure](02-git-and-project-structure.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [Phase 1 — Relational DB Concepts](../phase-1-databases/01-relational-db-concepts.md)
