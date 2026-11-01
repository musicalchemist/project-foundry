---
name: foundry-design
description: "Choose architecture and module boundaries or plan a behavior-preserving refactor when domain, data, interface, or operational tradeoffs need explicit design."
---

# Design a changeable boundary

Trace one primary use case and one failure through the current/proposed modules. Identify data ownership, domain terms, trust boundaries, and measured quality constraints.

Compare the simplest viable design with alternatives using complexity, reliability, changeability, testability, latency, cost, and ownership. Specify module responsibilities, public contracts, invariants, effects, and error behavior. Add compatibility, timeout/retry, and idempotency rules where applicable.

For refactors, identify callers and preserved behavior, establish characterization evidence, and split the change into reversible steps. Separate feature changes from behavior-preserving work.

Return a boundary/data-flow description, consequential ADRs with alternatives and revisit conditions, and the first implementable slice with verification. Propose a fitness check only for a constraint the project actually needs to preserve.
