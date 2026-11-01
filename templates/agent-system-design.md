# Agent system design

- User/task and simplest non-agent baseline:
- Prompt contract: inputs, constraints, examples, output schema.
- Context: sources, permissions, freshness, provenance, retrieval and memory.
- Harness: tools, validation, privilege levels, state, checkpoints, redacted traces.
- Loop: progress signal, verification, step/time/cost caps, repeated-failure limit.
- Graph: nodes, inputs/outputs, transition guards, branches, joins, cycles, error edges.
- Graph purpose: workflow/dependencies / knowledge/retrieval / causal assumptions; define evidence, identity, provenance and validation appropriate to that purpose.
- Effects: authorization, idempotency, deduplication and partial-effect recovery.
- Cancellation, escalation, failure fallback and termination evidence:
- Versioned eval cases, baseline comparison, stochastic variation:
- Missing/stale data, malformed output, injection, denial, timeout, budget exhaustion, and restart tests:
- Release/update owner, monitoring, privacy and retirement:
