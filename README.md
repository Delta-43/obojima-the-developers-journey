# Obojima - Diary of a Developer's Journey

A self-directed, project-based course to learn the full stack — relational
databases, ETL, Python/FastAPI backends, responsive HTML/CSS/JS/TypeScript,
React, and ML — by building a single product end to end: **Obojima
Potions**, a small D&D-inspired potion-brewing game based on the *Obojima —
Tales from the Tall Grass* sourcebook.

See [`IDEA.md`](IDEA.md) for the project's motivation and
[`course_plan/00-overview.md`](course_plan/00-overview.md) for the full
step-by-step curriculum.

Agent-facing docs: [`PLAN.md`](PLAN.md) (locked goals/decisions for AI
agents), [`MEMORY.md`](MEMORY.md) (running decisions/gotchas journal),
[`AGENTS.md`](AGENTS.md) (canonical, tool-agnostic behavioral contract for
the `course-guide` mentor), and [`SOUL.md`](SOUL.md) — the personality of
**Echo**, a whimsical spirit-professor of Obojima who teaches with examples
and riddles rather than handing over answers outright. Kept in this repo so
both can be ported to any AI coding tool/model. Thin adapters wire them into
specific tools: `.github/agents/course-guide.agent.md` for VS Code/Copilot,
`.claude/agents/course-guide.md` for Claude Code. Echo keeps this README and
`Progress.md` in sync as steps are completed.

## Toolchain

- **Database:** PostgreSQL
- **Backend:** Python 3.11+ / FastAPI
- **Frontend:** Vanilla HTML/CSS/JS+TypeScript first, then React
- **ML:** scikit-learn, then a small neural net (PyTorch or Keras/TensorFlow)

Exact tool versions are pinned as they're installed — see
[`course_plan/phase-0-foundations/01-tooling-and-environment-setup.md`](course_plan/phase-0-foundations/01-tooling-and-environment-setup.md).

## Phases

Each phase lives in `course_plan/` as a series of nudge-style step files (goal,
concepts to research, deliverable, acceptance criteria — no full hand-holding).
Phases are ordered so each one's output feeds the next: schema → ETL-loaded
data → API → UI → ML model plugged back into the API.

<!-- STATUS-TABLE:START -->
| # | Phase | Steps | Status |
|---|-------|-------|--------|
| 0 | [Foundations](course_plan/phase-0-foundations/01-tooling-and-environment-setup.md) | Tooling, Git, Python refresher | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
| 1 | [Relational Databases](course_plan/phase-1-databases/01-relational-db-concepts.md) | Concepts, schema design, PostgreSQL setup | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
| 2 | [ETL Pipeline](course_plan/phase-2-etl/01-etl-concepts.md) | Concepts, parsing raw data, load pipeline | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
| 3 | [Backend & APIs](course_plan/phase-3-backend/01-http-rest-api-concepts.md) | HTTP/REST, FastAPI, brewing logic, auth, tests | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
| 4 | [Frontend Fundamentals](course_plan/phase-4-frontend-fundamentals/01-html-css-basics.md) | HTML/CSS, responsive design, JS, TypeScript, API wiring | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
| 5 | [Frontend Framework](course_plan/phase-5-frontend-framework/01-react-fundamentals.md) | React fundamentals, UI rebuild, state/UX polish | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
| 6 | [Machine Learning](course_plan/phase-6-machine-learning/01-ml-concepts-and-data-prep.md) | Data prep, classical model, neural net, serving | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
| 7 | [Deployment & Capstone](course_plan/phase-7-deployment-and-capstone/01-containerization-and-deployment.md) | Containerization, deployment, retrospective | ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) |
<!-- STATUS-TABLE:END -->

**Legend:** ![Complete](https://img.shields.io/badge/status-complete-brightgreen) all steps checked off in `Progress.md` · ![In Progress](https://img.shields.io/badge/status-in%20progress-yellow) at least one step done · ![Not Started](https://img.shields.io/badge/status-not%20started-lightgrey) no steps done yet

## Progress

Full step-by-step checklist lives in [`Progress.md`](Progress.md) — check
items off there as each step is completed; update the table above to match.

| Phase | Progress | Notes |
|---|---|---|
| 0 — Foundations | 0 / 3 steps | Not started |
| 1 — Relational Databases | 0 / 3 steps | Not started |
| 2 — ETL Pipeline | 0 / 3 steps | Not started |
| 3 — Backend & APIs | 0 / 5 steps | Not started |
| 4 — Frontend Fundamentals | 0 / 5 steps | Not started |
| 5 — Frontend Framework | 0 / 3 steps | Not started |
| 6 — Machine Learning | 0 / 4 steps | Not started |
| 7 — Deployment & Capstone | 0 / 2 steps | Not started |