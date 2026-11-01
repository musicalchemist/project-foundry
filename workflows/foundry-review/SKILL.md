---
name: foundry-review
description: "Review a scoped change or existing component for actionable defects, contract violations, design risks, security boundaries, and missing verification evidence."
---

# Review against the contract

Trace the changed behavior through callers, interfaces, and tests. Prioritize acceptance/correctness failures, affected trust boundaries, compatibility, then maintainability and operation.

Each finding needs: location, reproducible trigger, consequence, evidence, and the smallest correction. Separate demonstrated defects from questions needing investigation. Omit style preferences without a concrete effect.

Apply only relevant checks:

- Refactor: preserved contracts and characterization coverage.
- Research: units, dependence, leakage, lineage, assumptions, and claim support.
- AI: held-out evaluation, retrieval/tool authorization, bounded failure, and cost.

Return findings by consequence, reviewed scope, and validation gaps. An absence of findings applies only to that scope. A review does not modify code unless fixes are requested.
