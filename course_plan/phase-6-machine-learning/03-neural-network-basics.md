# Phase 6 · Step 3 — Neural Network Basics

**Goal:** Build a small feed-forward neural network for the same brew-success prediction task, and compare it honestly against your Phase 6 Step 2 classical model.

## Why it matters
`IDEA.md`'s ML ambition includes deep learning fundamentals. A tiny, well-understood network on tabular data is the right-sized first deep learning project — resist the urge to over-scale this.

## Concepts to research
- Neurons, layers, weights/biases, and activation functions (ReLU, sigmoid) at a conceptual level
- Forward pass, loss functions (binary cross-entropy for this task), and backpropagation (conceptually — you don't need to derive the math by hand)
- Training loop basics: epochs, batches, learning rate, and what an optimizer (e.g. Adam) does
- Overfitting in neural nets specifically, and simple mitigations (dropout, early stopping, or just a small enough network for your dataset size)
- Choosing a framework: PyTorch or TensorFlow/Keras — pick one and note why

## Deliverable
- `ml/train_nn.py` (or notebook) implementing a small feed-forward network (2-3 hidden layers is plenty for this dataset size) for the same classification task as Step 2
- A training curve (loss over epochs) plotted or logged
- A head-to-head comparison against the Step 2 classical model on the same test set and metrics

## Acceptance criteria
- [ ] You can explain what each layer of your network is doing, even briefly
- [ ] The training loss decreases over epochs (or you can explain why it doesn't, and what you tried)
- [ ] The neural net is evaluated with the same metrics and same test set as Step 2, for a fair comparison
- [ ] You've written an honest verdict: did the neural net actually beat the classical model here, and does that make sense given your dataset's size and complexity?

## Hints
- On a small, mostly-tabular dataset like this, it's a completely valid and common outcome for a simple neural net to *not* beat logistic regression/trees — that's a real, useful lesson about when deep learning is (and isn't) the right tool.
- Keep the network small; this step is about understanding the mechanics, not squeezing out state-of-the-art performance.

---
**Previous:** [02 — Classical Model: Brew Success Prediction](02-classical-model-success-prediction.md) | **Up:** [Course Overview](../00-overview.md) | **Next:** [04 — Serving the Model from the API](04-serving-the-model-from-the-api.md)
