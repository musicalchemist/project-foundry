# Prompt, context, harness, loop, and graph engineering

These are useful design categories rather than a requirement to build a complex agent framework. Describe the concrete system first. Graph engineering can involve workflow/dependency graphs, knowledge graphs, or causal graphs; identify which problem the graph should solve before selecting tools.

| Discipline | What you design | Evidence it works |
| --- | --- | --- |
| Prompt engineering | Task instructions, examples, output contracts | Behavior on representative cases and counterexamples |
| Context engineering | Information/tool selection, retrieval, memory, freshness | Correct evidence arrives within the budget without unauthorized content |
| Harness engineering | Runtime around the model: tools, permissions, state, evaluation | Correct execution, traceability, containment, and recovery |
| Loop engineering | Repeated observation, action, verification, and stopping | Progress within caps, correct termination, and safe handling of failure |
| Graph engineering | States, transitions, dependencies, branching, joins, and cycles | Reachable outcomes, valid transitions, and bounded failure paths |

## Prompt contracts

Specify the goal, inputs, constraints, success criteria, and required output structure. Give examples that clarify difficult boundaries; include ambiguity and refusal/escalation cases when relevant. Separate instructions from quoted/retrieved data. Version prompts with their eval results. Require schemas or validated tool arguments for machine-consumed output.

Treat model output as a proposal requiring validation at consequential boundaries. Do not rely on a prompt to enforce access control. Keep reasoning requests focused on concise explanations, evidence, and decisions; verification does not require access to hidden model reasoning.

## Context as an information pipeline

Identify what each step needs and where it comes from. Track provenance, timestamp/version, permissions, and uncertainty. Retrieve only relevant evidence, enforce document authorization before retrieval, and distinguish instructions from source material. Account for missing and stale data explicitly.

Use stable identifiers and file paths for recoverable information. Offload large artifacts and logs to permitted storage, then load small excerpts as needed. Keep durable decisions and handoffs separate from temporary tool output. Compaction should preserve goals, constraints, unresolved questions, and evidence pointers. Revalidate state after resuming.

Start with explicit reads/search and bounded retrieval. Add vector search, knowledge graphs, or long-term memory only when evaluation demonstrates the need. Avoid treating a full context window as a target.

## The harness

The harness executes tools, applies permissions, stores state, validates schemas, handles retries/timeouts, records redacted traces, and connects evaluation to the runtime. Keep these responsibilities testable apart from the model.

Define tool contracts, privilege levels, allowed destinations, and idempotency keys. Record model/version/settings, prompt/context versions, state transitions, tool outcomes, costs where available, and final evidence. Treat credentials and private context as protected assets. Persist only permitted data. Test with simulated failures and safe fixtures before real external side effects.

Support cancellation, checkpoints, resumable work, and bounded recovery. A durable run should know which effect already happened. Avoid performing it twice after a crash. Distinguish a retryable transient failure from a permanent validation or permission failure.

## Bounded loops

Design each loop with an objective, state, progress signal, verification method, maximum steps/time/cost, repeated-failure limit, cancellation path, and escalation/stop conditions. Successful termination requires evidence, not the model’s confidence. If the loop cannot improve the relevant signal, stop or change the approach.

For a coding task, the signal might be a reproduced failing test becoming green with a reviewed diff. For a literature investigation, it might be coverage of specific questions with primary evidence, under a search cap. For research, distinguish exploratory iteration from confirmatory analysis; repeated tuning cannot consume the held-out set without invalidating it.

Retry tool calls only if safe and appropriate. Validate before irreversible writes; use idempotency, deduplication, and explicit effect records where retries could repeat external actions. An automated loop does not gain additional authority by running longer.

## Graphs and state machines

Start with a sequential loop. Use a DAG for independent tasks with prerequisites; a state machine for interactive branching or approvals; and explicit cycles for bounded refinement. Define node inputs/outputs, state ownership, transition guards, error edges, joins, and termination. At joins, validate consistency and resolve conflicts before proceeding.

For example: intake → feasibility spike → plan → build → verify. Verification can return to build under a retry cap. Release requires verified evidence and applicable authority. A graph edge cannot substitute for a required human decision.

Use graph checks to detect unreachable success states, cycles without caps, waits without timeouts, duplicate effects, concurrent writers, and failure branches that lose evidence. Task graphs organize dependencies; causal graphs express assumptions about causation. Do not confuse dependency ordering with scientific causal identification.

For knowledge graphs, define entities, typed relations, identity resolution, schema constraints, source provenance, confidence, temporal validity, and access rules. Evaluate the queries the graph must answer and compare with simpler tables or search. Incorrect entity merges or unsupported edges can produce plausible but false conclusions. Version graph updates and preserve the evidence behind relations. A graph-based retrieval system still needs authorization and answer-grounding evaluation.

For causal graphs, state the variables, directed relationships, domain assumptions, unobserved confounding, and the inference/identification question. The graph expresses assumptions that require justification; it does not prove them. Use appropriate methods review before treating graph structure as evidence of an intervention effect.

## Evaluate the complete system

Test prompts, retrieval/context quality, tool behavior, loop termination, graph transitions, and end-to-end outcomes separately. Include missing data, stale evidence, malformed output, prompt injection, tool failure, permission denial, cancellation, budget exhaustion, and restart after a partial effect.

Measure accepted task completion, correctness, human interventions, cost/time, and consequential failure rate on a versioned case set. Compare with a simpler baseline. Keep development cases separate from held-out evaluation and record stochastic variation. Add machinery only when it improves a measured failure mode.
