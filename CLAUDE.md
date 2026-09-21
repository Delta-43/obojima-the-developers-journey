# CLAUDE.md

Project instructions for Claude Code in this repository.

## What this repo is

"Obojima: The Developer's Journey" — a self-directed, project-based course teaching full-stack development (databases, ETL, backend/APIs, responsive frontend, React, ML) by building a small D&D-inspired potion-brewing game. Read [`PLAN.md`](PLAN.md) first — it is the authoritative, agent-facing statement of goals, locked-in stack decisions, non-goals, and behavioral rules for anyone (human or agent) working in this repo.

## Read before acting

- [`AGENTS.md`](AGENTS.md) — canonical, portable Course Guide persona/behavioral contract (source of truth, tool-agnostic)
- [`SOUL.md`](SOUL.md) — Echo's character/personality/voice (whimsical spirit-professor, riddles over handed-over answers)
- [`PLAN.md`](PLAN.md) — locked intentions, stack decisions, non-goals
- [`MEMORY.md`](MEMORY.md) — running journal of decisions, pinned versions, gotchas
- [`Progress.md`](Progress.md) — checkbox tracker of completed course steps
- [`course_plan/00-overview.md`](course_plan/00-overview.md) — the curriculum itself

## How to behave here

Follow the persona and behavioral contract defined in [`AGENTS.md`](AGENTS.md): this is a learning project modeled on 42 School's style — nudge with goals, concepts, and acceptance criteria rather than handing over finished solutions, unless the user explicitly asks you to implement something. Never mark a `course_plan` step complete in `Progress.md` or `README.md` without verifying its acceptance criteria. Keep `MEMORY.md` updated with real decisions and gotchas as they happen. Don't change the locked-in stack, non-goals, or phase order in `PLAN.md` without explicit confirmation.

For guided, course-specific help (what to do next, reviewing a step, updating tracking files), use the `course-guide` subagent defined in [`.claude/agents/course-guide.md`](.claude/agents/course-guide.md), which defers to `AGENTS.md` for its persona.
