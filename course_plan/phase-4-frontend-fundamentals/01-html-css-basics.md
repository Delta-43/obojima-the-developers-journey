# Phase 4 · Step 1 — HTML & CSS Basics

**Goal:** Build a static, unstyled-then-styled HTML page for the potion game's core screen (e.g. a list of ingredients and a potion-brewing panel), with no JavaScript yet.

## Why it matters
Before adding interactivity or a framework, you need to be fluent in semantic HTML and core CSS — the foundation everything visual sits on.

## Concepts to research
- Semantic HTML elements (`header`, `main`, `section`, `button`, `form`, lists) vs. div-soup
- The CSS box model, specificity, and the cascade
- Flexbox for laying out a card grid (ingredient cards, potion cards)
- Basic accessibility: alt text for ingredient images, label/input associations, sufficient color contrast

## Deliverable
- `frontend/index.html` + `frontend/styles.css` (no build tools yet, no JS) rendering:
  - A grid/list of ingredient cards (name, image, rarity) using placeholder or real data hardcoded for now
  - A potion detail view mockup
- No responsiveness required yet (next step) — but semantic and accessible markup is required now

## Acceptance criteria
- [ ] The page validates as reasonable semantic HTML (no `<div>` standing in for `<button>`, headings used hierarchically)
- [ ] All images have meaningful `alt` text
- [ ] Styling uses an external stylesheet, not inline styles or excessive `!important`
- [ ] You can explain, for at least one element, why you chose a Flexbox layout over floats/positioning

## Hints
- It's fine — expected, even — to hardcode a handful of ingredients/potions directly in the HTML for now. Wiring to the real API is Step 5 of this phase.
- Reuse the artwork in `raw_assets/extracted_images_arts/` and `extracted_images_potions/` for realistic placeholders.

---
**Previous:** [Phase 3 — Testing the API](../phase-3-backend/05-testing-the-api.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [02 — Responsive Web Design](02-responsive-web-design.md)
