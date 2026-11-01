---
name: foundry-harness
description: "Design or evaluate an agent runtime using prompt/context contracts, authorized tools, bounded loops, explicit workflow graphs, checkpoints, and end-to-end evidence."
---

# Design a bounded agent runtime

Compare the task with a sequential/non-agent baseline. Specify:

- Prompt: inputs, constraints, examples, validated output contract.
- Context: provenance, freshness, access filtering, retrieval, memory, and compaction invariants.
- Harness: tool schemas/privileges, validation, state ownership, redacted traces, checkpoints, cancellation.
- Loop: progress signal, verification, step/time/cost cap, repeated-failure limit, termination/escalation.
- Workflow graph: node contracts, guards, joins, error edges, cycle caps, concurrency ownership.

Record external effects so retry/restart cannot duplicate them. Check deadlocks, unreachable outcomes, conflicting writers, and partial-effect recovery. Add graph machinery only for a demonstrated branching/durability need; workflow dependencies do not establish causal claims.

Evaluate components and end-to-end outcomes on development and held-out cases: stale/missing context, malformed outputs, injection, denial, timeout, budget exhaustion, cancellation, and partial-effect restart.

Return system design, baseline comparison, measured correctness/cost/time where available, operating limits, and the first verified increment.
