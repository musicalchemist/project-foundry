---
name: to-tickets
description: "Turn an agreed plan, specification, or conversation into verifiable local tasks with acceptance criteria and explicit blocking dependencies."
disable-model-invocation: true
---

# Turn a plan into tasks

Read the agreed scope and relevant repo contracts, glossary, and decisions. Flag a missing decision that prevents decomposition rather than inventing it. Use a named local destination from the task or existing project conventions; otherwise propose `docs/project/tasks/<feature>/`.

Split work into independently demonstrable or verifiable slices. An app slice crosses the layers needed for one behavior; a research slice produces one inspectable result with its data/protocol prerequisites. Size tasks so an agent can finish and verify each in one bounded session. Separate capped investigations from implementation when feasibility is unresolved.

For each task, record only dependencies that actually gate it. Distinguish a technical blocker from a preferred order. Detect cycles and unresolved external prerequisites before marking work ready. Identify the tasks whose blockers are satisfied; those form the ready frontier, not an instruction to launch agents.

For broad mechanical refactors, use expand–contract: introduce a compatible form, migrate callers in verifiable batches, then remove the old form after all migrations. If intermediate changes cannot pass checks separately, identify the integration branch and final verification gate explicitly.

Present the breakdown with titles, outcomes, and blockers. Resolve material scope, granularity, or ordering choices; reuse an already-approved breakdown without another approval loop. Write one local Markdown file per task in dependency order:

```md
# 01: Task title

Outcome: Observable behavior or inspectable research artifact.
Blocked by: Task IDs, a named external prerequisite, or none.
Status: proposed | ready | blocked | done

- [ ] Acceptance evidence

Verification: Relevant command, comparison, or inspection.
Stop condition: Budget, failed prerequisite, or evidence requiring replanning.
```

Use project terminology. Include stable interfaces or decision-rich snippets only when they materially remove ambiguity. Return task paths, the dependency map, and the first ready task. This workflow writes local tasks; publishing tracker issues or running implementation requires a separate request.
