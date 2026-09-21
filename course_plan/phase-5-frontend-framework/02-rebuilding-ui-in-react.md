# Phase 5 · Step 2 — Rebuilding the UI in React

**Goal:** Rebuild the vanilla TS game UI from Phase 4 as a proper React + TypeScript application, componentizing the ingredient list, potion view, and brewing panel.

## Why it matters
This is where you feel the payoff of a component model: the same features from Phase 4, but organized in a way that scales as the UI grows.

## Concepts to research
- Breaking a UI into components (what's a component's natural boundary — an `IngredientCard`, an `IngredientGrid`, a `BrewPanel`?)
- Lifting state up when sibling components need to share it (e.g. selected ingredients shared between the grid and the brew panel)
- Typed props with TypeScript interfaces
- Data fetching patterns in React (a custom hook like `useIngredients()` wrapping `fetch`, or a library like TanStack Query if you want to go a step further)

## Deliverable
- `frontend/` (or a new `frontend-react/` if you want to keep the vanilla version around for comparison) rebuilding all Phase 4 functionality:
  - Ingredient grid, potion detail view, login form, brew panel — as components
  - Same real API calls to your FastAPI backend

## Acceptance criteria
- [ ] No component is a "God component" containing all the logic — responsibilities are split sensibly
- [ ] Shared state (selected ingredients, auth token/current user) lives at an appropriate common ancestor, not duplicated
- [ ] TypeScript types for API responses are shared/reused consistently across components
- [ ] The rebuilt app has full feature parity with the Phase 4 vanilla version

## Hints
- Don't reach for a global state library (Redux, Zustand, etc.) yet unless prop-drilling becomes genuinely painful — Step 3 covers that decision explicitly.

---
**Previous:** [01 — React Fundamentals](01-react-fundamentals.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [03 — State Management & UX Polish](03-state-management-and-ux-polish.md)
