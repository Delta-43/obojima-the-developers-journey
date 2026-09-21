# Phase 2 · Step 1 — ETL Concepts

**Goal:** Understand Extract-Transform-Load (and its cousin ELT) well enough to design a pipeline that turns messy sourcebook data into clean rows in your database.

## Why it matters
`raw_assets/potions_data.md` (and the associated `.json`/images) is unstructured, human-readable text — not database rows. You need a repeatable, re-runnable process to go from "raw text extracted from a PDF" to "structured ingredient/potion records," because you'll be doing this again whenever new potions/ingredients are added.

## Concepts to research
- ETL vs. ELT — where the "transform" step happens relative to loading, and why it matters for scale (you don't need to worry about scale here, but understand the distinction)
- Idempotency: running your pipeline twice should not create duplicate rows or crash
- Data validation/cleaning: handling missing fields, inconsistent naming, encoding issues (the raw text has OCR/PDF-extraction artifacts — expect messy data)
- Staging vs. final tables (optional pattern: load raw parsed data into a staging table/structure first, validate, then upsert into the real schema)

## Deliverable
A short `etl/README.md` describing, in your own words, the pipeline you're about to build:
- What the input is (raw files in `raw_assets/`)
- What the output is (rows in `ingredients`, `potions`, `potion_ingredients`)
- What "safe to re-run" means for your specific pipeline

## Acceptance criteria
- [ ] You can explain what would go wrong if you ran a naive `INSERT`-only script twice
- [ ] You've decided your re-run strategy (e.g. `INSERT ... ON CONFLICT DO UPDATE`, or truncate-and-reload, or a diff-based upsert) and written down why
- [ ] You've skimmed `raw_assets/potions_data.md` and `potions_data.json` and listed at least 3 data-quality issues you'll need to handle (e.g. broken characters, merged fields, missing images for some entries)

## Hints
- Open `raw_assets/potions_data.json` — it's a raw PDF content dump, not directly usable; `potions_data.md` is the more human-readable extraction and is probably your better starting point for parsing.
- You don't need a workflow orchestrator (Airflow etc.) for a project this size — a well-structured Python script is the right tool. Save orchestration frameworks for a "next steps" idea in your capstone retrospective.

---
**Previous:** [Phase 1 — PostgreSQL Setup](../phase-1-databases/03-postgresql-setup.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [02 — Parsing the Raw Sourcebook Data](02-parsing-raw-source-data.md)
