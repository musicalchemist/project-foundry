---
name: foundry-build
description: "Implement, debug, or incrementally refactor a scoped task with meaningful verification and reviewable changes in an existing or newly scoped project."
---

# Implement one verified slice

Turn acceptance criteria into an observable check before editing. For a bug, reproduce the failure, minimize it, and test a hypothesis. For logic with a stable interface, use TDD in vertical slices. For a refactor, establish characterization evidence and compare behavior after each boundary move.

Inspect callers and affected invariants before choosing the edit. Verify through public interfaces; expected values must come from a spec, worked example, or independent reference rather than repeating the implementation.

Run the relevant fast check per slice, then the project's required gates for the completed change. Investigate new failures; record existing failures separately. Repeat expensive checks only after a relevant change or new concern.

Return the changed contract/behavior, evidence from the actual interface, check commands/results, and unresolved acceptance criteria. Stop a failing attempt loop when no new hypothesis or evidence justifies another attempt.
