# Obojima: The Developer's Journey — Course Overview

A self-directed, project-based curriculum for learning the full stack — from relational databases to ETL, backend APIs, responsive frontend, and machine learning — by building **Obojima Potions**, a small D&D-inspired potion-brewing game based on the *Obojima — Tales from the Tall Grass* sourcebook.

This is not a hand-holding tutorial. Each step gives you a goal, the concepts you need to research, a concrete deliverable, and acceptance criteria — similar in spirit to a 42 School project subject. You decide the implementation. Track your progress in [`Progress.md`](../Progress.md).

## Who this is for

You're comfortable programming (Python, C, R) but have never shipped a full web app end-to-end, and JavaScript is new to you. Every phase assumes you can learn a new syntax quickly but need guidance on *architecture* and *sequencing* — what to build, in what order, and why.

## The product

A mini-game where a player combines ingredients to brew potions:
- **Ingredients** have a type (plant, mineral, creature part, machine part, etc.) and a rarity (common/uncommon/rare).
- **Potions** belong to a category (combat/utility/whimsy) and a rarity, and are the result of combining specific ingredients.
- **Users** have stats/skill levels that affect their chance of successfully brewing a potion.
- A **success/failure prediction model** estimates brewing outcome based on the chosen ingredients and the user's level.

Source data lives in [`raw_assets/`](../raw_assets/) (extracted from the sourcebook as `potions_data.md`/`.json` plus artwork). You'll design an ETL pipeline to turn that raw material into structured, related database records.

## Chosen stack

| Concern | Choice |
|---|---|
| Database | PostgreSQL |
| Backend | Python + FastAPI |
| Frontend fundamentals | Vanilla HTML/CSS/JS first |
| Frontend framework | React (after fundamentals are solid) |
| ML | scikit-learn first, then a small neural net |

Pin exact versions as you install them and note them in `course_plan` phase notes or a root `NOTES.md` — future-you will thank you.

## Phase map

| Phase | Theme | Folder |
|---|---|---|
| 0 | Foundations: tooling, Git, Python refresher | [`phase-0-foundations/`](phase-0-foundations/01-tooling-and-environment-setup.md) |
| 1 | Relational databases & schema design | [`phase-1-databases/`](phase-1-databases/01-relational-db-concepts.md) |
| 2 | ETL: raw sourcebook data → structured DB | [`phase-2-etl/`](phase-2-etl/01-etl-concepts.md) |
| 3 | Backend & APIs (FastAPI) | [`phase-3-backend/`](phase-3-backend/01-http-rest-api-concepts.md) |
| 4 | Frontend fundamentals (HTML/CSS/JS/TS) | [`phase-4-frontend-fundamentals/`](phase-4-frontend-fundamentals/01-html-css-basics.md) |
| 5 | Frontend framework (React) | [`phase-5-frontend-framework/`](phase-5-frontend-framework/01-react-fundamentals.md) |
| 6 | Machine learning (brew success prediction) | [`phase-6-machine-learning/`](phase-6-machine-learning/01-ml-concepts-and-data-prep.md) |
| 7 | Deployment & capstone retrospective | [`phase-7-deployment-and-capstone/`](phase-7-deployment-and-capstone/01-containerization-and-deployment.md) |

Phases are ordered so each one produces an artifact the next one depends on: schema → data in the DB → an API over that data → a UI consuming the API → a model plugged back into the API.

## How to use each step file

Every step follows the same shape:
1. **Goal** — the outcome, not the method.
2. **Why it matters** — how it serves the final product.
3. **Concepts to research** — terms to go learn elsewhere (docs, articles, videos) before or while building.
4. **Deliverable** — the concrete thing that should exist in the repo when you're done.
5. **Acceptance criteria** — a checklist to self-verify before moving on.
6. **Hints** — nudges if you get stuck, not solutions.

When a step is done, check it off in [`Progress.md`](../Progress.md) and move to the next linked step.

**Start here:** [Phase 0, Step 1 — Tooling & Environment Setup](phase-0-foundations/01-tooling-and-environment-setup.md)
