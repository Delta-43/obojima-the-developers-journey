# Phase 4 · Step 2 — Responsive Web Design

**Goal:** Make the static page from Step 1 work well from mobile widths up to desktop, using modern responsive CSS techniques.

## Why it matters
"Responsive Web Design" is an explicit goal in `IDEA.md` — and a game UI with cards/grids is a great vehicle for learning it properly.

## Concepts to research
- Mobile-first CSS and why it's the recommended default direction
- Media queries and choosing breakpoints based on your content, not arbitrary device widths
- Responsive units (`rem`, `%`, `vw`/`vh`, `clamp()`) vs. fixed pixel values
- CSS Grid for more complex responsive layouts (complementing the Flexbox from Step 1)
- Responsive images (`srcset`/`sizes`, or at minimum `max-width: 100%`)

## Deliverable
- The Step 1 page updated to reflow sensibly at three rough breakpoints: narrow (phone), medium (tablet), wide (desktop)
- At least one layout that changes structurally (not just shrinks) between breakpoints — e.g. a card grid that goes from 1 column to 2 to 4

## Acceptance criteria
- [ ] The page is usable and readable at ~375px width with no horizontal scrolling
- [ ] Breakpoints are chosen because content started breaking, not copy-pasted from a random source
- [ ] Images scale down properly on narrow viewports instead of overflowing
- [ ] You can resize the browser continuously and nothing "jumps" awkwardly at the boundary points

## Hints
- Use your browser's device toolbar/responsive mode while building, not just at the end.
- Design mobile-first (base styles for narrow screens, `min-width` media queries adding complexity for wider ones) — it's usually less CSS overall than desktop-first.

---
**Previous:** [01 — HTML & CSS Basics](01-html-css-basics.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [03 — JavaScript Fundamentals](03-javascript-fundamentals.md)
