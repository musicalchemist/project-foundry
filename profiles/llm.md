# LLM applications and LLMOps profile

Use for assistants, generation, extraction, retrieval, and tool-using systems. Define representative tasks, failure costs, data boundaries, quality thresholds, and cost/latency budget. Compare a simpler deterministic or search-based baseline.

Build a versioned evaluation set before broad optimization: typical tasks, edge cases, unanswerable questions, adversarial input, authorization boundaries, and tool failures. Separate development cases from held-out evaluation. Use deterministic checks for schemas/tool outcomes and grounded human review for subjective quality. Calibrate model-based judges against human judgments and record limitations.

Version prompts, model/provider identifiers, settings, context/retrieval configuration, tool schemas, and datasets. Record reproducible run metadata and redacted traces. Provider updates can change behavior; retest material changes. Measure quality, task completion, correctness/grounding, refusals/escalations, latency, and cost where available.

For retrieval, evaluate access filtering, source freshness, coverage, relevance, provenance, and citation fidelity separately from answer quality. Enforce permissions before the content reaches the model. Keep instructions separate from retrieved data; test prompt injection and leakage. Do not treat citations as proof without checking their support.

For tools, validate arguments and outputs, enforce least privilege in the runtime, require appropriate authority for consequential effects, and cap steps/time/cost. Define retries, idempotency, cancellation, checkpoints, and repeated-failure handling. Use explicit graph/state design when branching or durable workflows make it valuable.

Use deterministic extraction and structured output where practical. Consider retrieval, prompt/context changes, smaller task decomposition, or fine-tuning based on measured failure modes and actual data rights. Add complexity only with comparative evidence. Define provider/model fallback, human escalation, release gates, privacy-aware monitoring, and recovery from bad prompts or model versions.
