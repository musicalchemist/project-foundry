# Machine learning and MLOps profile

Use when a learned model supports a real research or product objective. Define the decision/task, target variable, data generation process, baseline, metric, error costs, and acceptable latency/compute. Start with a simple heuristic or statistical baseline.

Create a data contract and lineage record. Check labels, missingness, duplicates, drift, class imbalance, subgroup coverage, consent/license, and leakage. Split by the actual independent unit, time, site, or subject when needed. Fit transforms only on the training portion. Keep held-out evaluation independent of model selection.

Record code commit/source version, environment, data/split identifiers, preprocessing, parameters, seeds, hardware, training cost, metrics, and artifacts for each run. Use meaningful comparisons, calibration and uncertainty checks where applicable, subgroup/error analysis, robustness tests, and justified statistical comparisons. A headline metric alone is insufficient.

Test preprocessing, feature schemas, numerical invariants, and training/serving consistency. Use small deterministic fixtures in ordinary CI; expensive training belongs in a separately budgeted pipeline. Package the entire inference path, including preprocessing and thresholds, with the model.

For deployment, version datasets, models, and APIs; define artifact registration, promotion criteria, compatibility checks, rollout/recovery, and owner. Monitor inputs, predictions, performance when ground truth arrives, latency, cost, and drift. A drift signal triggers investigation; it does not by itself prove deterioration or authorize automatic retraining.

Define a controlled retraining process with new evaluation evidence. Keep a model card and incident/fallback plan. Sensitive or consequential predictions require project-specific expert review and safeguards. Retirement includes artifact/data retention and removing obsolete endpoints.
