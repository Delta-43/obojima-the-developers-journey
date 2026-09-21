# Bootstrap Prompt — Obojima: The Developer's Journey

This file is a reusable prompt for recreating the initial documentation, curriculum, and agent configuration for this repository. Paste the prompt below into a capable coding agent while it is working at the root of a new Git repository.

Before using it, place any legally obtained source material you want the course to use in `raw_assets/`. The agent must treat those files as user-supplied reference material: it may inspect and transform them for the project, but it must not reproduce copyrighted sourcebook content in the generated curriculum or documentation.

---

## Prompt

Create the initial repository structure for **Obojima: The Developer's Journey**, a self-directed, project-based full-stack development course. The learner will build one product incrementally: **Obojima Potions**, a small D&D-inspired potion-brewing web game.

Do not build the application yet. Your task is to create the course plan, project-governance documents, progress tracking, and portable AI-agent configuration that will guide its later implementation.

### 1. Learner and teaching model

Assume the learner:

- Is already comfortable programming in Python, C, and R.
- Can learn new syntax independently.
- Is new to JavaScript and to shipping a complete web application.
- Most needs help with architecture, sequencing, engineering practices, and understanding why each component exists.

Model the curriculum after:

- freeCodeCamp's small, incremental progression, where each step builds on previous work.
- 42 School's project style, where requirements and acceptance criteria guide the learner without providing a complete implementation.

Each course step must explain the goal and relevant concepts but stop short of giving a finished solution. The course guide may provide complete code only when the learner explicitly asks for it.

### 2. Product concept

The final product is a potion-brewing game in which:

- Ingredients have properties such as type and rarity.
- Potions have categories, rarity, difficulty, and recipes composed of ingredients.
- Users have skill levels or stats that affect brewing outcomes.
- A player selects ingredients and attempts to brew a potion.
- Backend business logic determines the result and updates user state.
- A machine-learning model eventually estimates the chance of brewing success from the chosen ingredients and user level.
- Relevant user-supplied artwork may be associated with ingredients or potions.

Use files in `raw_assets/` as source data for the later ETL phase. Inspect the available files before designing that phase, but do not modify, regenerate, or duplicate the source assets during repository bootstrap. If the assets are missing, create the curriculum anyway and clearly document that they are a prerequisite for the ETL work.

### 3. Locked technical decisions

Treat these as deliberate choices that must not be changed without asking the user:

| Concern | Decision |
|---|---|
| Database | One PostgreSQL relational database with related tables—not separate databases for ingredients, potions, and users |
| Backend | Python 3.11+ and FastAPI |
| Frontend fundamentals | Vanilla HTML/CSS/JavaScript, followed by TypeScript |
| Frontend framework | React, introduced only after frontend fundamentals |
| Machine learning | scikit-learn first, then one small feed-forward neural network using PyTorch or Keras/TensorFlow |
| Repository shape | One monorepo that will eventually contain `backend/`, `database/`, `etl/`, `frontend/`, and `ml/` |

Exact dependency and tool versions are not yet selected. The learner must choose, pin, and record them during the relevant course steps.

### 4. Scope boundaries

Keep these out of the MVP unless the user explicitly changes scope:

- Multiplayer, trading, or a player economy.
- Native mobile applications.
- Production-scale infrastructure or premature performance engineering.
- Workflow orchestrators such as Airflow for the ETL pipeline.
- Deep learning beyond one small educational neural network.
- Payments, monetization, or production email/account infrastructure.

Do not create application source code, dependency manifests, CI workflows, or pretend build/test commands during bootstrap. Those artifacts must appear only when their course steps call for them.

### 5. Curriculum sequence

Create `course_plan/00-overview.md` and linked step files for these phases:

1. **Foundations**
   - Tooling and environment setup.
   - Git and project structure.
   - Python refresher for engineers.
2. **Relational databases**
   - Relational database concepts.
   - Schema design for ingredients, potions, recipes, and users.
   - PostgreSQL setup.
3. **ETL pipeline**
   - ETL concepts and the distinction between ETL and ELT.
   - Parsing the user-supplied raw source data.
   - Loading data idempotently into PostgreSQL.
4. **Backend and APIs**
   - HTTP and REST concepts.
   - Initial FastAPI endpoints.
   - Potion-brewing business logic.
   - Authentication and user accounts at an educational MVP scope.
   - API testing.
5. **Frontend fundamentals**
   - HTML and CSS basics.
   - Responsive web design.
   - JavaScript fundamentals.
   - TypeScript basics.
   - Consuming the API with vanilla JavaScript.
6. **Frontend framework**
   - React fundamentals.
   - Rebuilding the UI in React.
   - State management and UX polish.
7. **Machine learning**
   - ML concepts and data preparation.
   - A classical brew-success prediction model.
   - Neural-network basics.
   - Serving the selected model from the API.
8. **Deployment and capstone**
   - Containerization and deployment.
   - Retrospective and next steps.

Sequence the phases so each produces an input needed by the next:

`schema -> loaded data -> API -> browser UI -> React UI -> trained model -> model-backed API -> deployment`

Do not introduce later-phase implementation work early unless the learner explicitly asks to prototype out of order.

Every step file must contain:

1. Goal.
2. Why it matters to the final product.
3. Concepts to research.
4. A concrete deliverable.
5. Verifiable acceptance criteria.
6. Hints that nudge without giving the complete solution.
7. Navigation links to the overview and adjacent steps.

### 6. Repository documents

Create and cross-link these root files:

- `README.md` — public project overview, toolchain, phase table, status badges, and per-phase progress counts.
- `PLAN.md` — authoritative agent-facing goals, locked decisions, non-goals, sequencing rules, behavioral contract, and project success criteria.
- `Progress.md` — one checkbox per course step, linked to its step file.
- `MEMORY.md` — append-only journal template for decisions, pinned versions, gotchas, lessons, and open questions.
- `AGENTS.md` — canonical, tool-neutral Course Guide persona and behavior contract.
- `SOUL.md` — the Course Guide's personality and voice.
- `IDEA.md` — preserve this reusable bootstrap specification so another repository can be recreated from it.

Treat `PLAN.md` as authoritative after bootstrap. `IDEA.md` explains how to recreate the starting repository; it is not a substitute for the live plan once the project evolves.

Keep `README.md` and `Progress.md` synchronized. Never mark a step complete until its acceptance criteria have been checked against actual repository evidence.

### 7. Course Guide agent

Create a portable Course Guide named **Echo**.

`AGENTS.md` must be the single source of truth for Echo's functional behavior:

- Read `PLAN.md`, `MEMORY.md`, `Progress.md`, and the relevant course step before advising or reviewing work.
- Default to concepts, targeted questions, and acceptance criteria rather than finished implementations.
- Provide code or a complete implementation when the user explicitly requests it.
- Verify every acceptance criterion before marking a step complete.
- When a step is complete, update `Progress.md`, the corresponding README status/count, and any genuine decision or gotcha in `MEMORY.md`.
- Never change locked stack decisions, non-goals, or phase ordering without explicit user confirmation.
- Do not start a later phase while earlier required phases remain incomplete unless the user explicitly asks to jump ahead.

`SOUL.md` must define Echo as a warm, witty, whimsical spirit-professor from Obojima who:

- Calls the learner "apprentice" sparingly.
- Explains technical concepts plainly before using a potion- or magic-themed analogy.
- Usually ends teaching moments with a short, solvable question or riddle.
- Never allows character flavor to obscure correctness or slow down precise technical work.
- Drops the riddle habit when the user asks for exact code, commands, or direct implementation.

Keep personality separate from function: change behavior in `AGENTS.md` and voice in `SOUL.md`.

### 8. Tool integrations

Create thin adapters instead of duplicating the agent definition:

- `.github/copilot-instructions.md` — repository-wide Copilot instructions that point to `AGENTS.md`, `SOUL.md`, `PLAN.md`, `MEMORY.md`, and `Progress.md`; describe the current bootstrap-only state and warn Copilot not to invent build or test commands.
- `.github/agents/course-guide.agent.md` — a discoverable GitHub Copilot custom agent that delegates its persona and rules to `AGENTS.md` and `SOUL.md`.
- `CLAUDE.md` — repository instructions for Claude Code that identify `PLAN.md` and `AGENTS.md` as authoritative.
- `.claude/agents/course-guide.md` — a discoverable Claude Code subagent that delegates to `AGENTS.md` and `SOUL.md`.

Use the current documented frontmatter and tool names for each target platform rather than guessing. Keep adapters short so shared behavior cannot drift between tools.

### 9. Quality and consistency checks

Before finishing:

- Verify that every Markdown link you created resolves to an existing repository file.
- Verify that `Progress.md` contains exactly one checkbox for every course step.
- Verify that README phase counts match `Progress.md`.
- Verify that every step has all seven required sections and correct previous/next navigation.
- Verify that all tool-specific adapters point to the canonical `AGENTS.md` and `SOUL.md`.
- Verify that no course step is marked complete.
- Verify that no application code, dependencies, generated assets, or fictitious commands were added.
- Preserve all pre-existing files unless a change is required by this prompt.

Summarize the generated structure, any assumptions made, and any source assets that were expected but missing. Ask questions before implementation only when a missing decision would materially change the repository architecture; otherwise use the defaults above.

