## What I Reviewed
- Found two reference notebooks in the repo:
  - `NOAI2025-Section_2_Questions.ipynb` (linear regression via gradient descent, 2D k-means, simple RAG via TF and cosine similarity)
  - `NOAI2025-Section2Solutions.ipynb` (complete NumPy solutions for the above)
- Difficulty level: moderate — multi-feature gradient descent, 2D k-means with convergence check, and a miniature TF/cosine pipeline.

## Constraints and Requirements
- Create three new Upper Secondary task notebooks using NumPy only:
  - `sample25_sec_upper_taskb1.ipynb`: Supervised learning (NumPy)
  - `sample25_sec_upper_taskb2.ipynb`: Unsupervised learning (NumPy)
  - `sample25_sec_upper_taskb3.ipynb`: AI agents (NumPy) with planning/tool-use/guardrails
- Provide matching solutions:
  - `sample25_sec_upper_taskb1soln.ipynb`, `sample25_sec_upper_taskb2soln.ipynb`, `sample25_sec_upper_taskb3soln.ipynb`
- Each task must include structured parts: (a) structured theory problems, (b) design challenge, (c) practical programming.
- Must be simpler than the reference notebooks and fully runnable; confirm correctness.

## Proposed Tasks (less difficult than references)
### Task B1 — Supervised Learning (NumPy)
- **Dataset**: tiny 1D synthetic dataset (e.g., study_hours → score), `X` shaped `(m, 1)` and `y` shaped `(m,)`.
- **Theory (short answers)**: define supervised learning; discuss MSE and the role of learning-rate; simple bias/variance prompt.
- **Design Challenge**: pick a learning-rate schedule (constant vs. simple decay) and justify; describe stopping criteria.
- **Programming**: implement 1D linear regression via gradient descent with:
  - initialise `theta` to zeros; compute gradient; update `theta`; run for `N` iterations;
  - return `theta` and predictions; round outputs to 4 decimals.
- **Tests**: assert approximate `theta` and predicted values against provided expected numbers.
- **Why simpler**: single-feature GD (vs multi-feature), smaller dataset, fixed iteration; no matrix multiplications beyond simple vector ops.

### Task B2 — Unsupervised Learning (NumPy)
- **Dataset**: small 1D points (e.g., `[1, 2, 3, 9, 10, 11]`), `k=2`.
- **Theory**: define unsupervised learning; what is k-means objective; handling empty clusters.
- **Design Challenge**: choose initialisation (fixed seeds provided) and stopping criteria; discuss effect of `k`.
- **Programming**: implement 1D k-means:
  - compute distances to centroids; assign; update centroids via mean; iterate with `max_iter`;
  - return final centroids rounded to 4 decimals and cluster assignments.
- **Tests**: check centroids equal expected (e.g., `[2.0, 10.0]`) and assignments match expected groups.
- **Why simpler**: 1D instead of 2D; fewer points; explicit helper functions and convergence checks simplified.

### Task B3 — AI Agents (NumPy) — minimal, offline and testable
- **Scope alignment**: planning, tool-use, single vs multi-agent comparison, evaluation, guardrails/logging.
- **Theory**: outline an agent loop (sense → plan → act); list possible risks and corresponding guardrails (permissions, step limit, logs).
- **Design Challenge**: design a tiny task board (array-based) and compare:
  - single-agent (generalist) vs dual-agent (planner + executor) flow diagrams.
- **Programming**: implement a minimal agent framework:
  - tools implemented with NumPy (e.g., `sum_array`, `mean_array`, `threshold_classify`) operating on provided arrays;
  - a stub "LLM planner" function (deterministic rule-based selector) that maps task strings to a tool call sequence (simulates step-wise planning without external APIs);
  - agent classes with per-step guardrails: allowed-tools whitelist, max-steps, result logging; sandboxed inputs (NumPy arrays only);
  - evaluation metrics: success rate on a small fixed set of tasks; simple runtime counts; error taxonomy (e.g., tool-not-allowed, max-steps-exceeded).
- **Tests**: unit tests to confirm tool outputs, that both single-agent and multi-agent can solve at least N of M tasks; metrics match expected values.
- **Why simpler**: fully deterministic, no external LLM; uses NumPy for data ops; focuses on planning and guardrails rather than NLP.

## Notebook Structure (all six notebooks)
- Title and overview cell.
- "Instructions" cell with constraints: NumPy-only; no network access.
- Provided data/constants cell.
- Theory Q&A cell(s) (markdown prompts; students write brief answers in markdown).
- Design challenge cell(s) (markdown + optional small code stub to sketch config).
- Programming tasks with scaffolded function signatures and TODO comments.
- Tests cell with assertions/prints and expected outputs for self-checking.
- Final reflection cell (students explain approach).

## Validation and Correctness
- I will implement and run each solution notebook locally to ensure:
  - All tests pass deterministically on Python 3.9+ with NumPy only.
  - Outputs match expected rounded values.
  - No external dependencies, I/O, or non-deterministic behaviour.
- Difficulty justification: B1/B2 reduce dimensionality and dataset size versus the references; B3 avoids text vectorisation and external LLM, using deterministic planning over NumPy tools.

## Deliverables
- `sample25_sec_upper_taskb1.ipynb` and `sample25_sec_upper_taskb1soln.ipynb`
- `sample25_sec_upper_taskb2.ipynb` and `sample25_sec_upper_taskb2soln.ipynb`
- `sample25_sec_upper_taskb3.ipynb` and `sample25_sec_upper_taskb3soln.ipynb`

## Next Steps
- Generate the six notebooks with the structures above.
- Run and verify solutions; adjust expected outputs to ensure reliable autograding.
- Hand back files for your review.