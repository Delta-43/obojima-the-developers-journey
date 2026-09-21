# Phase 6 · Step 4 — Serving the Model from the API

**Goal:** Wire your chosen trained model back into the FastAPI backend so real brew attempts are scored (or at least previewed) using the learned model instead of only the hand-written formula.

## Why it matters
A model that only lives in a notebook has no product value. This step closes the loop from `IDEA.md`'s original goal: predicting success/failure for a real choice of ingredients and user level.

## Concepts to research
- Loading a serialized model efficiently at API startup (not reloading it per-request)
- Keeping training-time feature engineering and inference-time feature engineering in sync (the classic "training/serving skew" bug)
- Deciding the product behavior: does the model *replace* the Phase 3 formula, run *alongside* it as a preview ("your estimated odds: 72%"), or gate it behind a feature flag while you compare both in production data?
- Basic model versioning (knowing which model file is currently live)

## Deliverable
- A new or updated endpoint (e.g. `GET /brew-attempts/predict` or a field added to the existing brew flow) that runs the trained model on the requested ingredients/user and returns a success probability
- Documentation of which model (classical or neural net) is served, and why
- The frontend (Phase 5) updated to show this predicted probability to the user before they commit to brewing, if you choose to surface it in the UI

## Acceptance criteria
- [ ] The same feature-engineering code (or a shared, tested equivalent) is used at training time and at inference time
- [ ] A prediction request returns a probability, not just a hardcoded pass-through of the Phase 3 formula
- [ ] Model loading doesn't measurably slow down every request (loaded once, not per-request)
- [ ] You've manually verified at least one prediction makes intuitive sense (e.g. a well-matched, high-rarity ingredient set with a high-skill user predicts a high success probability)

## Hints
- If the classical model and neural net disagree noticeably, that's worth investigating and writing up in your Phase 7 retrospective — it's a genuine, interesting finding, not a failure.

---
**Previous:** [03 — Neural Network Basics](03-neural-network-basics.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [Phase 7 — Containerization & Deployment](../phase-7-deployment-and-capstone/01-containerization-and-deployment.md)
