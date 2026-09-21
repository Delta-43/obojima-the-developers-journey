# Phase 5 · Step 1 — React Fundamentals

**Goal:** Learn React's core mental model (components, props, state, effects) with a small throwaway app before touching your real game UI.

## Why it matters
Jumping straight into rebuilding a real app in a new framework is harder than learning the framework's ideas in isolation first, on something disposable.

## Concepts to research
- Components as functions, JSX syntax
- Props vs. state, and the "data flows down, events flow up" mental model
- `useState` and `useEffect` — and why effects exist (side effects like data fetching)
- Lists and keys (`.map()` rendering with a stable `key`)
- Controlled form inputs

## Deliverable
- A small, separate scratch React app (e.g. a counter, or a simple filterable list) built with Vite, unrelated to the potion game
- Not part of the final product — this is purely a learning sandbox, safe to delete afterward

## Acceptance criteria
- [ ] You can explain, unprompted, the difference between props and state
- [ ] Your scratch app fetches at least one piece of data asynchronously using `useEffect` and renders a loading state
- [ ] A list in your scratch app is rendered with proper stable `key`s (not array index, unless you can justify why that's safe here)

## Hints
- Keep this step short — the goal is conceptual comfort, not a polished app. Move to the real rebuild in Step 2 once the core hooks feel natural.

---
**Previous:** [Phase 4 — Consuming the API](../phase-4-frontend-fundamentals/05-consuming-the-api-vanilla-js.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [02 — Rebuilding the UI in React](02-rebuilding-ui-in-react.md)
