---
name: foundry-ml
description: "Plan, compare, or operationalize ML/statistical models using leakage-safe data, baselines, reproducible experiments, error analysis, and controlled promotion."
---

# Compare a model with its baseline

Define the prediction/decision, error costs, baseline, acceptance metric, and compute/latency cap. Check label provenance, data rights, missingness, duplicates, and subgroup coverage.

Split at the independent subject/group/site/time unit. Fit preprocessing on training data only; keep selection/tuning separate from held-out evaluation.

Record data/split/code/environment versions, parameters/seeds, hardware, and model artifacts. Compare the baseline and candidates using error/subgroup analysis, calibration/uncertainty where relevant, and robustness. Test preprocessing/schema/numerical invariants with small fixtures.

For operation, version the entire inference path, including preprocessing and thresholds. Specify promotion evidence, training/serving parity, owner, fallback/recovery, delayed-ground-truth monitoring, and retraining conditions.

Return experiment/evaluation evidence and a model card. Drift triggers investigation; it neither proves quality loss nor satisfies promotion criteria.
