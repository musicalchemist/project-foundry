# Code and architecture decisions

Choose the simplest design that meets the current behavior, quality constraints, and plausible next changes. Architecture is a set of tradeoffs that becomes visible in code, interfaces, data, deployment, and operations.

## Start with constraints

Identify users, domain terms, core use cases, data sensitivity, latency, reliability, scale, cost, and expected change. Separate measured requirements from guesses. Inspect existing project conventions. Compare viable options and record consequential choices with alternatives, evidence, and a condition for revisiting them.

For most new small products, a modular monolith or a small application with clear boundaries is a reasonable candidate. Separate services when independent scaling, ownership, deployment, or isolation justifies their operational cost. Choose serverless, containers, jobs, or local tools based on workload and team capacity rather than fashion.

## Modules that reduce cognitive load

- Group related domain behavior. Keep business/scientific logic independent of UI, persistence, and vendor APIs where it makes testing and change easier.
- Give each module a clear responsibility and a small, useful interface. Hide implementation details and enforce invariants at boundaries.
- Avoid circular dependencies, shared mutable state, and cross-module database shortcuts that undermine ownership.
- Use domain names consistently. Add a small glossary when terminology is contested or complex. DDD is useful for rich domains; bounded contexts do not mandate separate services.
- Introduce abstractions for repeated knowledge or demonstrated variation. Similar-looking code may represent different concepts. Avoid generic frameworks for a single use case.
- Keep effects explicit: time, randomness, filesystem, network, database, and external model calls. Make them controllable in tests without mocking every internal function.

Function length, class counts, and directory depth are signals to inspect, not universal quality thresholds. Readability comes from clear names, coherent control flow, limited hidden behavior, and interfaces that match the problem. Use comments to explain invariants, tradeoffs, and surprising mechanisms.

## Data and failure behavior

Define schemas, ownership, identifiers, units, null/missing semantics, and versioning. Validate at trust boundaries. Describe error types and recovery behavior. For asynchronous or distributed work, specify consistency, ordering, idempotency, duplicate delivery, retry caps, timeouts, cancellation, and partial failure. Add caches only with an invalidation and freshness strategy.

Plan schema/API changes for compatibility. A production migration may need expand/contract steps, a backfill, rollback limits, and a recovery plan. A research pipeline needs immutable raw inputs and recorded transformations; overwriting raw data makes conclusions hard to audit.

## Refactor with evidence

Separate behavior changes from broad cleanup when it improves review. Characterize observable behavior before risky refactors, move in small increments, and keep meaningful tests green. Delete dead code after verifying use. Avoid rewriting an unfamiliar component solely to match a preferred pattern.

Architecture fitness functions turn important constraints into checks: forbidden dependency cycles, API compatibility, latency bounds, tenant isolation, or reproducibility. Pick checks tied to actual constraints. Avoid asserting every implementation detail.

## Review a design

Trace a primary use case and a failure case through the proposed modules. Identify the hardest future change and the largest failure radius. Verify that operational ownership, security, and testing fit the design. Keep an ADR for choices expensive to reverse, not every local naming decision.

## Keep a thin map of the system

Let names, interfaces, and tests explain implementation. Maintain a short code/navigation map, domain glossary when useful, consequential ADRs, and the project's current strategy or constraints. Document why, contracts, and non-obvious boundaries; avoid prose that repeats every function. Update affected documentation in the same change and remove obsolete claims.

For an unfamiliar system, trace one actual user action through entrypoints, modules, data, and external services. Link map elements to inspected source paths and distinguish observed connections from inferred ones. A small Mermaid diagram is usually enough; add an interactive map only when navigation warrants it. Update the affected flow after changes, record what was inspected, and treat a map's health observations as leads rather than a security audit. [Floorplan](https://github.com/haydenschmitty/floorplan) is an inspected reference for this mapping idea; no plugin, renderer, server, or helper is required.
