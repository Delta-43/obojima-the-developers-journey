# Phase 1 · Step 2 — Schema Design (Ingredients, Potions, Users)

**Goal:** Design the actual relational schema for the three domains from `IDEA.md`: ingredients, potions, and users — including how they relate to each other.

## Why it matters
This schema is the backbone of the entire product. Every later phase (ETL loads into it, the API reads/writes it, the ML model trains on data shaped by it) depends on getting the relationships right now.

## Concepts to research
- Look at `raw_assets/potions_data.md` to see the real domain vocabulary: potion **types** (combat/utility/whimsy), potion **rarities** (common/uncommon/rare), ingredient **rarities**, ingredient **categories** (plant, mineral, creature part, machine part, etc.)
- Many-to-many design between potions and ingredients (a potion recipe needs a set of ingredients; an ingredient can appear in multiple recipes) — this needs a junction table with its own attributes (e.g. quantity)
- Designing a `users` table for a game: what stats does a brewer need? (skill/level, XP, inventory of owned ingredients?)
- Designing a table to record **brew attempts** (user + chosen ingredients + potion targeted + outcome) — you'll need this historical data later for ML, so plan for it now even if it's empty until Phase 3
- Enum-like fields in SQL: `CHECK` constraints vs. a separate lookup table (e.g. a `rarities` table) — pros/cons of each

## Deliverable
A `database/schema.md` (or `.dbml`/diagram of your choice) documenting:
- `ingredients` table (name, category, rarity, description, image reference, etc.)
- `potions` table (name, type, rarity, description, image reference, etc.)
- `potion_ingredients` junction table linking potions to their required ingredients
- `users` table (username, skill/level stats, created_at, etc.)
- `brew_attempts` table (user_id, potion_id, ingredients used, success/failure, timestamp) — this is your future ML training data
- An ER diagram (text-based with arrows is fine, or a tool like dbdiagram.io/drawio)

## Acceptance criteria
- [ ] Every table has an explicit primary key
- [ ] Every foreign key relationship is documented with its `ON DELETE` behavior decided (not left as a default you didn't think about)
- [ ] You can explain what happens if an ingredient used in a `brew_attempts` row is later deleted
- [ ] The schema supports: "list all ingredients needed for potion X" and "list all potions a user has successfully brewed" as straightforward queries

## Hints
- Don't design for hypothetical future features you haven't been asked for (e.g. trading between users) — YAGNI applies to schemas too.
- It's fine (expected) to revise this schema slightly once you hit real data in Phase 2 — treat this as a strong draft, not a contract set in stone.

---
**Previous:** [01 — Relational DB Concepts](01-relational-db-concepts.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [03 — PostgreSQL Setup](03-postgresql-setup.md)
