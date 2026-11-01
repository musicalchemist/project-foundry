---
name: foundry-llm
description: "Design or improve an LLM application with versioned evaluations, prompt/context changes, grounded retrieval, authorized tools, and quality/cost/latency evidence."
---

# Change LLM behavior against an eval

Define task/output contracts, failure costs, data/tool boundaries, baseline, and budget. Separate development cases from held-out cases covering normal, edge, unanswerable, adversarial, authorization, and tool-failure behavior.

Use deterministic checks for schemas/tool outcomes and a human rubric for subjective quality. Calibrate model judges against humans. Evaluate retrieval relevance, freshness, authorization, and citation support separately from generation.

Change one demonstrated failure mode through prompts, context, retrieval, decomposition, settings, or fine-tuning. Version provider/model, prompt/context, tool schemas, settings, and cases. Report quality, repeated-run variation, cost, and latency where measured.

For tools, validate arguments/effects outside the model; test injection/leakage, cancellation, caps, idempotency, and fallback.

Return the baseline comparison, supported change, unresolved failure classes, release blockers, and monitoring/update conditions. Retuning on held-out cases requires a new independent evaluation set.
