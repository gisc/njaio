## Overview
Create three Lower Secondary Section B notebooks aligned to the learning outcomes and lighter than Upper Secondary tasks:
- B1: Structured theory (application/evaluation only)
- B2: Unsupervised learning (NumPy)
- B3: Simple rule-based agents (NumPy) with human-in-the-loop and safeguards
Also add links in `secondary_lower.html` Sample Paper section similar to Upper Secondary.

## Deliverables
- `sample25_sec_lower_taskb1.ipynb` (question-only, structured theory)
- `sample25_sec_lower_taskb2.ipynb` (question + programming)
- `sample25_sec_lower_taskb2soln.ipynb` (solutions)
- `sample25_sec_lower_taskb3.ipynb` (question + programming)
- `sample25_sec_lower_taskb3soln.ipynb` (solutions)
- Update `secondary_lower.html` tile to list:
  - Section A: MCQ (existing)
  - Section B Task 1 Question
  - Section B Task 2 Question / Solution
  - Section B Task 3 Question / Solution

## Task B1 — Structured Theory (application/evaluation)
Scope derived from `secondary_lower.html` outcomes:
- Human‑Centred & Everyday AI: convenience vs privacy; human responsibility; media influence.
- Ethics, Safety & Fairness: dataset bias; misinformation/surveillance; safeguards.
- AI Techniques & Applications: ML pipeline basics; symbolic vs statistical.
- AI System Design: problem framing; datasets & metrics; failure cases.
Structure:
- 6–8 short scenario prompts where students:
  - analyse trade‑offs and justify choices (application)
  - evaluate risks/bias and propose safeguards (evaluation)
  - choose symbolic vs statistical with rationale (application)
  - specify datasets/metrics and identify potential failure cases (evaluation)
Notebook cells: markdown prompts, answer areas; no coding cells.

## Task B2 — Unsupervised Learning (NumPy)
- Data: very small 1D points (e.g., `[1,2,3,8,9,10]`) to cluster into `k=2`.
- Programming: implement 1D k‑means (assign/update/converge) in NumPy.
- Theory: 2–3 prompts (objective, effect of k, handling empty clusters).
- Tests: verify final centroids (≈ `[2.0, 9.0]`) and expected assignments.
- Solution notebook provides a working implementation and passes tests.

## Task B3 — Simple Agents (NumPy)
Scope differences (simpler):
- Define the agent loop (sense → plan → act) with clear goals and limits.
- Build a simple rule/block‑based agent to complete a task; test edge cases.
- Use human‑in‑the‑loop approvals and privacy‑by‑design for safe actions.
Programming:
- Tools: simple NumPy functions (e.g., `sum_array`, `threshold_flag`).
- Planner: deterministic rule selector mapping task type to tool (no LLM).
- Agent: requires an approval flag before executing; max‑steps limit; logs.
- Tests: confirm agent completes tasks when approved; blocks when not; handles edge cases (empty arrays, out‑of‑range).
- Solution notebook includes correct, deterministic implementation.

## Site Update
- Modify `secondary_lower.html` Sample Paper tile to show a two‑column layout:
  - Left: Section A: MCQ
  - Right: Section B links (Task 1 Question; Task 2 Question/Solution; Task 3 Question/Solution)

## Verification
- Run B2/B3 solutions locally to ensure deterministic outputs and passing assertions.
- Confirm no external libraries beyond NumPy; no network/file I/O.
- Ensure tasks are simpler than Upper Secondary (1D clustering, rule‑based agents rather than multi‑agent planning).

## Next Steps
- Generate the five notebooks and update `secondary_lower.html` links.
- Execute and validate B2/B3 solutions; adjust expected numbers where needed.
- Hand back for review.