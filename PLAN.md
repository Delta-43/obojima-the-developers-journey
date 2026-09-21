# PLAN.md — Agent-Facing Project Plan

This file is the authoritative, agent-facing statement of intent for this repository. It exists so any AI agent (or human) picking up this repo cold can understand what this project is, what is locked in, what is out of scope, and how it expects to be worked on — without having to infer it from conversation history.

If something here conflicts with a casual instruction given mid-conversation, prefer this file unless the user explicitly says they're changing the plan.

## 1. Project identity

- **Product:** Obojima Potions — a small D&D-inspired potion-brewing game (combine ingredients, brew potions, succeed/fail based on a formula/model and user skill).
- **Real purpose:** a personal, publishable, project-based course teaching the author full-stack development from first principles, one working increment at a time.
- **Motivation source:** [`IDEA.md`](IDEA.md) (informal, original brief — read for tone and inspiration, not as a spec).
- **Domain source data:** [`raw_assets/`](raw_assets/) — an extraction of the potion-brewing chapter from the *Obojima — Tales from the Tall Grass* sourcebook (~130 ingredients, potion recipes, artwork).

## 2. Source-of-truth file map

| File | Purpose | Who updates it | Update frequency |
|---|---|---|---|
| [`IDEA.md`](IDEA.md) | Original informal brief. Historical context only. | Nobody (frozen) | Never |
| `PLAN.md` (this file) | Locked intentions, goals, non-goals, behavioral contract | Human, with explicit confirmation | Rarely |
| [`MEMORY.md`](MEMORY.md) | Running journal: decisions made, versions pinned, gotchas, lessons learned | Agent + human, continuously | Every session with progress |
| [`Progress.md`](Progress.md) | Checkbox-level completion tracker, mirrors `course_plan/` steps | Agent, when a step is verifiably complete | Every completed step |
| [`README.md`](README.md) | Public-facing status: toolchain, phase table with badges, progress summary | Agent, kept in sync with `Progress.md` | Every completed step |
| [`course_plan/`](course_plan/00-overview.md) | The curriculum itself: phase/step goals, concepts, deliverables, acceptance criteria | Human, with agent assistance, only when deliberately revising the curriculum | Rarely, deliberately |

## 3. Locked-in stack decisions

Do not change these without explicitly confirming with the user first — they were chosen deliberately in course planning, not arbitrarily.

| Concern | Choice |
|---|---|
| Database | PostgreSQL |
| Backend | Python 3.11+ / FastAPI |
| Frontend fundamentals | Vanilla HTML/CSS/JS, then TypeScript |
| Frontend framework | React |
| ML | scikit-learn (classical) → a small neural net (PyTorch or Keras/TensorFlow) |
| Repo shape | Single monorepo: `backend/`, `database/`, `etl/`, `frontend/`, `ml/`, `course_plan/`, `raw_assets/` |

## 4. Learning goals (in priority order, from `IDEA.md`)

1. Relational databases (design + PostgreSQL)
2. ETL/ELT processes (raw sourcebook data → structured DB)
3. Python engineering practices + backend/API development (FastAPI)
4. Responsive web design + JavaScript/TypeScript + frontend libraries (React)
5. ML techniques (predicting potion brew success/failure)

## 5. Non-goals (explicitly out of scope for the MVP)

Do not silently add these — if the user wants one, treat it as a deliberate scope change, not a default:
- Multiplayer features, trading, or a player-vs-player economy
- A native mobile app (responsive web is sufficient)
- Production-scale performance/infrastructure (this is a learning project, not a scaled service)
- Workflow orchestration frameworks (Airflow, etc.) for the ETL pipeline — a well-structured script is the right scope
- Any deep learning beyond a small feed-forward network for the ML phase
- Monetization, payments, or real accounts/emails infrastructure

## 6. Sequencing rules

Phases in `course_plan/` are ordered so each one's output is the next one's input: schema → ETL-loaded data → API → UI → ML model plugged back into the API. Do not build a later phase's deliverable before an earlier phase's acceptance criteria are met, unless the user explicitly asks to jump ahead or prototype out of order.

## 7. Behavioral contract for agents working in this repo

- **Nudge, don't solve.** This is a learning project modeled on 42 School's style: give direction, concepts, and acceptance criteria — not complete solutions — unless the user explicitly asks you to write the implementation for them.
- **Ground yourself before advising.** Read the relevant `course_plan/phase-X/*.md` step file, [`Progress.md`](Progress.md), and [`MEMORY.md`](MEMORY.md) before answering "what should I do next" or reviewing work.
- **Track honestly.** Only check off a step in `Progress.md` (and update the `README.md` phase table) once its acceptance criteria are actually met — never mark something done speculatively or because the user says they're "basically done."
- **Keep `MEMORY.md` current.** When a real decision, gotcha, or pinned version comes up, record it there — don't let it live only in chat history.
- **Ask before locked-in changes.** Changing the stack table in Section 3, the phase sequence, or this file's contents requires explicit user confirmation first.
- **Respect the chosen pacing.** The user opted for many small, incremental steps (freeCDampCamp-style granularity) with 42-style non-hand-holding descriptions — don't collapse steps or skip acceptance criteria to move faster.

## 8. Success criteria

The project is "done" (for the MVP) when:
- [ ] Every step in [`Progress.md`](Progress.md) is checked off
- [ ] The app runs end to end: a user can register, log in, browse ingredients/potions, attempt a brew, and see a prediction informed by the trained model
- [ ] The app is deployed and reachable at a public URL
- [ ] [`RETROSPECTIVE.md`](RETROSPECTIVE.md) (created in the final course step) documents lessons learned and next steps

## 9. Changing this plan

If the user wants to change a locked-in decision (Section 3), a non-goal (Section 5), or the sequencing rules (Section 6), confirm explicitly, then update this file directly and note the change (with a one-line reason) in [`MEMORY.md`](MEMORY.md).
