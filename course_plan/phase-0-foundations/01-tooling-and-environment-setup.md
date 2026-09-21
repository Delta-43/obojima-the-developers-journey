# Phase 0 · Step 1 — Tooling & Environment Setup

**Goal:** Have a reproducible local dev environment ready for a multi-language project (Python backend, SQL, JS/TS frontend) before writing any product code.

## Why it matters
Every later phase assumes you can spin up a database, run a Python service, and serve static files without fighting your machine. Get this friction out of the way now.

## Concepts to research
- Python virtual environments (`venv`) and why you never install project deps globally
- Package managers: `pip` + `requirements.txt` (or `pyproject.toml` if you want to learn `uv`/`poetry`)
- Node.js and `npm`/`pnpm` — needed later for the JS/TS/React phases, install it now
- What a `.gitignore` is for and why secrets/venvs/`node_modules` never get committed
- The idea of "one repo, multiple services" (backend/, frontend/, ml/ as separate concerns)

## Deliverable
- Python 3.11+ installed, a virtual environment creation command you can repeat
- Node.js (LTS) installed and verified
- PostgreSQL installed locally (or via Docker — your choice, but decide now)
- A root `.gitignore` covering Python, Node, and OS/editor cruft
- A short `NOTES.md` (or section in `README.md`) recording exact tool versions installed

## Acceptance criteria
- [ ] `python --version` and `node --version` both run from a terminal in this repo
- [ ] You can create and activate a virtual environment and it's excluded from git
- [ ] PostgreSQL is running locally and you can connect to it with a client (`psql`, TablePlus, DBeaver, etc.)
- [ ] `git status` shows a clean tree with no venv/`node_modules`/build artifacts tracked

## Hints
- Don't install Postgres inside WSL/Docker unless you're already comfortable with that — optimize for reducing friction, not for extra learning right now.
- Recording versions now saves you hours of "works on my machine" debugging later.

---
**Up:** [Course Overview](../00-overview.md) | **Next:** [02 — Git & Project Structure](02-git-and-project-structure.md)
