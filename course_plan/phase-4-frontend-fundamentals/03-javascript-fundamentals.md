# Phase 4 · Step 3 — JavaScript Fundamentals

**Goal:** Learn core JavaScript by making the static page from Steps 1-2 interactive — no framework, no API calls yet, just the language and the DOM.

## Why it matters
This is your first real exposure to JS. Getting comfortable with the language and direct DOM manipulation now will make React (Phase 5) click much faster instead of feeling magical.

## Concepts to research
- Variables (`let`/`const`), functions (including arrow functions), and JS's type quirks vs. Python's
- Arrays/objects and their common methods (`map`, `filter`, `reduce`, `find`) — these will feel familiar coming from Python
- DOM selection and manipulation (`querySelector`, `addEventListener`, creating/updating elements)
- Events and event delegation
- The `this` keyword's quirks (a common gotcha coming from other languages) and why arrow functions behave differently

## Deliverable
- `frontend/app.js` that, without any framework:
  - Lets a user click ingredient cards to "select" them (visually toggled)
  - Shows a running list/summary of selected ingredients
  - Has a "Brew" button that (for now) just logs or displays the selection — no backend call yet
- Data can still be hardcoded in JS for this step

## Acceptance criteria
- [ ] All interactivity works with vanilla JS, no libraries
- [ ] Selecting/deselecting ingredients updates the UI without a page reload
- [ ] Your code avoids inline `onclick="..."` HTML attributes in favor of `addEventListener`
- [ ] You can explain what event delegation is and whether you used it

## Hints
- Resist reaching for jQuery or any helper library — the point of this step is to get comfortable with the plain DOM APIs first.
- Keep functions small and named for what they do; this habit transfers directly into React components later.

---
**Previous:** [02 — Responsive Web Design](02-responsive-web-design.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [04 — TypeScript Basics](04-typescript-basics.md)
