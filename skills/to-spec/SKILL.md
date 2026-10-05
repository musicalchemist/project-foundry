---
name: to-spec
description: "Synthesize an agreed conversation and repo context into a local specification with scope, public contracts, and acceptance evidence."
disable-model-invocation: true
---

# Capture an agreed specification

Use decisions already made in the conversation and relevant repo context. Do not restart discovery or silently resolve conflicting requirements. Mark an unresolved assumption and ask only when it changes the scope or prevents a usable specification.

Trace the proposed behavior through existing public interfaces. Prefer existing test seams; propose a new boundary only when acceptance evidence cannot be obtained at a suitable current interface. Reuse agreed seams and acceptance criteria rather than requesting approval again.

Write local Markdown in the project's established specification location, or propose `docs/project/specs/<feature>.md`. Include:

- Problem, intended user or research question, and observable outcome.
- Agreed behavior or protocol, public contracts/invariants, and relevant failure cases.
- Scope, exclusions, compatibility requirements, and unresolved prerequisites.
- Acceptance evidence, including preserved behavior for refactors or estimand/comparator and validation for research.
- Consequential decisions and the first bounded implementation or investigation step.

Use domain terminology and link existing evidence or decisions rather than duplicating them. Separate facts, accepted decisions, and proposals. Return the path, unresolved blockers, and readiness verdict. This workflow creates a specification; task decomposition, tracker publication, and implementation are separate steps.
