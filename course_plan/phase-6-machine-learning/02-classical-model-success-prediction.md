# Phase 6 · Step 2 — Classical Model: Brew Success Prediction

**Goal:** Train a simple, interpretable scikit-learn model (e.g. logistic regression or a decision tree) to predict brew success/failure, and evaluate it properly.

## Why it matters
This is your first real ML model, and a strong baseline. Interpretable models also let you sanity-check *why* the model predicts what it does — valuable before reaching for anything more complex.

## Concepts to research
- Logistic regression and decision trees — how each works conceptually, and why you'd choose one over the other for a first pass
- Evaluation metrics for classification: accuracy, precision, recall, F1, confusion matrix — and why accuracy alone can be misleading with imbalanced classes
- Cross-validation vs. a single train/test split
- Model interpretability: inspecting feature importances/coefficients to sanity-check the model matches your intuition about the game's rules

## Deliverable
- `ml/train_classical.py` (or notebook) that trains at least two different classical models on the Step 1 dataset
- A comparison of their evaluation metrics
- The chosen best model serialized to disk (e.g. via `joblib`/`pickle`) with a documented format

## Acceptance criteria
- [ ] You report precision/recall/F1 (not just accuracy) for your chosen model
- [ ] You've inspected feature importances/coefficients and can explain whether they match your intuition (e.g. "higher user skill increases success probability" should hold)
- [ ] The model is evaluated on held-out test data, never seen during training
- [ ] The serialized model file can be loaded back into a fresh Python session and produce the same predictions

## Hints
- Don't chase a perfect score — if accuracy is suspiciously close to 100%, suspect data leakage from Step 1 before celebrating.
- Keep the serialized model and any encoders/scalers you fit together (e.g. in a single pickled pipeline) so Phase 6 Step 4 doesn't have to guess how to reproduce preprocessing.

---
**Previous:** [01 — ML Concepts & Data Prep](01-ml-concepts-and-data-prep.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [03 — Neural Network Basics](03-neural-network-basics.md)
