# Phase 2 · Step 2 — Parsing the Raw Sourcebook Data

**Goal:** Write the "Extract + Transform" half of the pipeline: parse `raw_assets/potions_data.md` (and cross-reference images) into clean, structured Python objects.

## Why it matters
This is the messy, real-world data-wrangling work every data/backend engineer does. The output of this step is the input to the loader in Step 3.

## Concepts to research
- Text parsing strategies: regular expressions vs. line-by-line state machines vs. a markdown parser library — pick based on how structured the source text actually is
- Associating extracted images (`raw_assets/extracted_images_potions/`, `extracted_images_arts/`) with the correct ingredient/potion record (matching by order, page number, or naming convention — inspect the files to figure out the association)
- Data modeling for the "transform" step: define Python `dataclass`/Pydantic models (`ParsedIngredient`, `ParsedPotion`) as your intermediate representation before touching the database
- Defensive parsing: logging/collecting rows that fail to parse instead of crashing the whole run

## Deliverable
- `etl/extract.py` (or a small module) that reads the raw source and produces a list of structured ingredient/potion records in memory (or as an intermediate JSON/CSV file)
- A report of parsing coverage: how many of the ~130 ingredients and how many potions were successfully parsed vs. skipped, and why

## Acceptance criteria
- [ ] Running the extractor is repeatable and deterministic (same input → same output)
- [ ] Parsed records include, at minimum: name, category/type, rarity, description, and an image reference where available
- [ ] Failures are logged with enough context to fix the parser, not silently dropped
- [ ] You can inspect a handful of parsed records and confirm they match the source text by eye

## Hints
- Don't aim for 100% automated perfection — for a handful of stubborn edge cases, it's reasonable to hand-correct a small JSON/CSV afterward rather than fighting a parser forever. Document which records were hand-fixed and why.
- Keep extraction (reading raw data) and transformation (cleaning/shaping it) as separate functions even if they live in the same file — it makes debugging much easier.

---
**Previous:** [01 — ETL Concepts](01-etl-concepts.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [03 — Load Pipeline & Idempotency](03-load-pipeline-and-idempotency.md)
