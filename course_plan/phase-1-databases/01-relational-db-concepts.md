# Phase 1 · Step 1 — Relational Database Concepts

**Goal:** Understand the theory you need before designing the actual schema: tables, keys, relationships, normalization, and basic SQL.

## Why it matters
The next step asks you to design 3+ related tables from scratch. If the vocabulary (primary key, foreign key, many-to-many, normalization) isn't solid, the schema will accrete problems that are painful to fix once real data is loaded.

## Concepts to research
- Tables, rows, columns, primary keys, foreign keys
- One-to-many vs. many-to-many relationships, and junction/association tables
- Normalization (1NF–3NF) — and *why* you'd deliberately denormalize sometimes
- Basic SQL: `SELECT`, `JOIN` (inner/left), `WHERE`, `GROUP BY`, `INSERT`, `UPDATE`
- Constraints: `NOT NULL`, `UNIQUE`, `CHECK`, foreign key `ON DELETE` behavior

## Deliverable
No code yet. Produce a short written artifact (`database/notes.md` or similar) containing:
- A plain-English definition, in your own words, of primary key / foreign key / many-to-many
- A hand-drawn or text-based ER sketch of *any* small domain (doesn't have to be potions yet) with at least one many-to-many relationship, to prove you understand the pattern before applying it

## Acceptance criteria
- [ ] You can explain why a potion-to-ingredient relationship is many-to-many (a potion needs multiple ingredients; an ingredient can appear in multiple potions)
- [ ] You can write a `JOIN` query by hand (on paper or in a scratch SQL file) across a 3-table example
- [ ] You know what a junction table is and when you need one

## Hints
- If you want to practice SQL syntax hands-on before touching Postgres, SQLite via a browser-based playground is a fine sandbox for this step only — you'll set up real PostgreSQL in Step 3.

---
**Previous:** [Phase 0 — Python Refresher](../phase-0-foundations/03-python-refresher-for-engineers.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [02 — Schema Design](02-schema-design.md)
