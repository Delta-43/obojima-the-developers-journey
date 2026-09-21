# Phase 4 · Step 4 — TypeScript Basics

**Goal:** Learn TypeScript's core value proposition — static types on top of JS — by converting your Step 3 script to TypeScript.

## Why it matters
`IDEA.md` explicitly lists JavaScript/TypeScript as a goal, and React + TypeScript is the modern default combination you'll use in Phase 5. Learning TS on a small, already-working script is much easier than learning it and React at the same time.

## Concepts to research
- Basic types (`string`, `number`, `boolean`, arrays, unions, `interface`/`type`)
- How TypeScript models your data shapes (an `Ingredient` interface, a `Potion` interface) — mirror your backend's Pydantic models conceptually
- The compiler (`tsc`) and how TS catches errors before runtime
- `strict` mode and why it's worth turning on from day one
- Optional properties and `null`/`undefined` handling — a common source of confusion coming from Python's simpler `None`

## Deliverable
- `frontend/app.ts` (compiled to JS, or run via a bundler/toolchain of your choice — Vite is a reasonable pick you'll reuse for React) replacing `app.js`
- `Ingredient`/`Potion`/`SelectedIngredient`-style interfaces defined and used to type your DOM logic

## Acceptance criteria
- [ ] The project compiles with `strict: true` and no `any` types left unaddressed (a few deliberate, commented `any`s are acceptable if justified)
- [ ] Function signatures have explicit parameter and return types where they aren't trivially inferred
- [ ] You've deliberately introduced and then fixed at least one type error, to see the compiler catch a real mistake

## Hints
- If you set up Vite here for TypeScript compilation, you'll reuse the same tool for the React app in Phase 5 — worth the small setup investment now.

---
**Previous:** [03 — JavaScript Fundamentals](03-javascript-fundamentals.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [05 — Consuming the API (Vanilla JS)](05-consuming-the-api-vanilla-js.md)
