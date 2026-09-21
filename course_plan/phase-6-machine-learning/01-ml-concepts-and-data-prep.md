# Phase 6 · Step 1 — ML Concepts & Data Prep

**Goal:** Understand the ML workflow (features, labels, train/test splits, overfitting) and prepare a real training dataset from your `brew_attempts` table.

## Why it matters
Your hand-written formula from Phase 3 generated the very data you'll now learn from. This step bridges "rule-based system" to "learned system" — a core ML concept.

## Concepts to research
- Features vs. labels: what inputs predict what outcome (ingredient rarities/types used, user skill level, potion targeted → success/failure)
- Train/validation/test splits and why you never evaluate on data you trained on
- Class imbalance (if successes vastly outnumber failures or vice versa) and why it matters for a binary outcome
- Feature engineering: turning categorical data (ingredient rarity, potion type) into numeric features (one-hot encoding, ordinal encoding where order is meaningful)
- Data leakage — a common beginner mistake (e.g. accidentally including the outcome itself as a feature)

## Deliverable
- `ml/data_prep.py` (or notebook) that pulls `brew_attempts` (joined with ingredients/potions/users as needed) from PostgreSQL and produces a clean, feature-engineered training dataset
- If your real `brew_attempts` table is too small/thin to train anything meaningful yet, write a documented, clearly-labeled synthetic data generator (using your Phase 3 formula with varied random inputs) to bootstrap a larger dataset — and say so explicitly in your write-up, since this is a real-world workaround, not a shortcut to hide

## Acceptance criteria
- [ ] You can state, in one sentence, what the label is and what each feature represents
- [ ] The dataset is split into train/test sets before any model touches it
- [ ] No feature in your dataset is derived from the outcome itself
- [ ] You've checked and documented the class balance of your label

## Hints
- pandas is the natural tool for this step — if you haven't used it before, this is a good moment to pick it up.
- Being honest about synthetic vs. real data in your write-up is part of the learning — real ML work constantly deals with insufficient real-world data.

---
**Previous:** [Phase 5 — State Management & UX Polish](../phase-5-frontend-framework/03-state-management-and-ux-polish.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [02 — Classical Model: Brew Success Prediction](02-classical-model-success-prediction.md)
