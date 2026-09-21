# Phase 5 · Step 3 — State Management & UX Polish

**Goal:** Address any real state-sharing pain points from Step 2, and polish the UX with proper loading/error/empty states and basic client-side routing.

## Why it matters
A real product needs more than a happy path: users will see loading spinners, hit errors, and navigate between views. This step is about production-grade polish, not new core features.

## Concepts to research
- When (and when not) to reach for a state management library vs. React Context vs. just lifting state — make a deliberate, justified choice for this app's actual complexity
- Client-side routing (e.g. React Router) for separate views: ingredient browser, potion browser, brew screen, login/profile
- Consistent loading/error/empty UI states across all data-fetching components
- Basic form validation feedback (e.g. on login/registration)

## Deliverable
- Routing between at least 3 distinct views/pages
- Every data-fetching component handles loading, error, and empty-result states visibly (not just the happy path)
- A documented decision (in `frontend/README.md` or similar) on your state management approach and why it fits this app's size

## Acceptance criteria
- [ ] Navigating between views doesn't lose necessary state unexpectedly (e.g. auth session persists across routes)
- [ ] Simulating a backend error (stop the server, or force a bad request) shows a real error message in the UI, not a blank screen or console-only error
- [ ] The app is still responsive (Phase 4, Step 2's concepts) after the React rebuild — check at mobile widths again

## Hints
- Re-test responsiveness after this phase — component-based CSS approaches (CSS modules, styled-components, Tailwind) sometimes reset assumptions from your original vanilla CSS.
- This is a strong point to consider the frontend "MVP-complete" and update `Progress.md` accordingly.

---
**Previous:** [02 — Rebuilding the UI in React](02-rebuilding-ui-in-react.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [Phase 6 — ML Concepts & Data Prep](../phase-6-machine-learning/01-ml-concepts-and-data-prep.md)
