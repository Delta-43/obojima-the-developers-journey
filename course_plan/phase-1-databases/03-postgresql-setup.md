# Phase 1 · Step 3 — PostgreSQL Setup

**Goal:** Stand up a real PostgreSQL database, translate your schema design into actual DDL, and version it with a migration tool.

## Why it matters
This is where the design from Step 2 becomes a running, queryable database that the ETL pipeline (Phase 2) and API (Phase 3) will both depend on.

## Concepts to research
- `CREATE TABLE` syntax, data types in Postgres (`SERIAL`/`IDENTITY`, `TEXT`, `NUMERIC`, `TIMESTAMP`, `BOOLEAN`, `ENUM` types)
- Migrations: why raw hand-run SQL doesn't scale, and what a migration tool gives you (Alembic is the natural choice since you're using Python/FastAPI later)
- Connection strings / DSNs and keeping credentials out of source control (`.env`)
- Basic `psql` usage or a GUI client for inspecting your own database

## Deliverable
- `database/migrations/` containing your first migration(s) that create all tables from Step 2's design
- The database running locally with all tables created and constraints in place
- A `database/README.md` documenting how to spin up the DB and run migrations from scratch

## Acceptance criteria
- [ ] Running your migration tool from a clean database creates the full schema with no manual SQL steps
- [ ] Foreign keys, unique constraints, and check constraints from your design are actually enforced (test by trying to violate one)
- [ ] You can connect with a client and manually `INSERT`/`SELECT` a row in each table
- [ ] Credentials/connection strings are not hardcoded or committed

## Hints
- Set up Alembic (or your chosen migration tool) even though it feels like overhead for an empty DB — you'll be very glad you did once the schema evolves.
- Seed a tiny handful of rows by hand first, just to sanity check constraints, before Phase 2 tries to load 130 ingredients at once.

---
**Previous:** [02 — Schema Design](02-schema-design.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [Phase 2 — ETL Concepts](../phase-2-etl/01-etl-concepts.md)
