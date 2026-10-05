---
name: implement
description: "Implement agreed work from a specification or selected tickets, verify it through incremental checks, and finish with standards/spec review."
disable-model-invocation: true
---

Identify the accepted specification or selected tickets, prerequisites, acceptance criteria, and agreed seams. Resolve a missing contract before implementing the dependent work; do not silently expand the selected ticket set.

Use [tdd](../tdd/SKILL.md) where it fits the pre-agreed seams. Implement vertical slices; run relevant type checks and focused tests after meaningful changes, then the project's required checks for the completed work. Investigate failures before continuing a dependent slice.

When the implementation is ready, use [code-review](../code-review/SKILL.md) on the actual change set and accepted spec. Correct demonstrated defects and rerun affected checks; a remaining blocked acceptance criterion is not completed work.

Return the implemented requirements, changed paths, verification results, review findings/disposition, and remaining work. A commit, publication, or deployment is a separate action requiring existing task authorization; implementing a ticket alone does not request it.
