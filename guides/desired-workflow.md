# Guided workflow with coding agents

Default: human-led planning and human-guided AI implementation, one selected ticket at a time. Use this for an idea, new application, feature, research tool, or codebase refactor. The procedure combines the referenced Matt Pocock workflow concepts with original implementation guidance. It needs no Docker installation, loop runner, or parallel agents.

For a narrow task whose scope and acceptance criteria are already settled, reuse that agreement. Scale the documents to the work; a small change can keep its spec, task, and completion record in one file.

## The sequence and its outputs

| Step | Workflow | Result needed before moving on |
| --- | --- | --- |
| Understand | `grill-me` or `grill-with-docs` | Shared understanding of the problem, constraints, preserved behavior, and unresolved choices |
| Reduce uncertainty, when needed | Bounded research or `prototype` | Evidence for a difficult assumption or feedback on a concrete design |
| Define the destination | `to-spec` | Accepted behavior, scope, public contracts, and observable acceptance criteria |
| Plan the work | `to-tickets` | Small verifiable slices linked to story/requirement IDs, blockers, and a first ready task |
| Build one selected slice | `implement`, using `tdd` where meaningful | A reviewable change and actual verification results |
| Check and decide | `code-review`, then human review/QA | Standards/spec findings and required acceptance checks resolved or recorded; decision about the next ticket |

These names refer to workflows in the selected Matt collection. Use the paths recorded for the adopted edition: invoke an installed skill using the host's supported interface, or ask the agent to read its actual `SKILL.md` explicitly. Do not download a skill, helper, or runner because a name appears here. The procedure below also works as standalone guidance without installed skills.

### Reach shared understanding with the human

For new work or a substantial refactor, start with `grill-me`; use `grill-with-docs` when a glossary and decision records should evolve alongside the interview. Work through dependencies between questions. Settle the intended outcome, exclusions, important tradeoffs, failure behavior, and evidence that would count as success. Planning remains human-in-the-loop in every execution mode.

In an existing repo, inspect the current code, callers, tests, instructions, and uncommitted work before proposing a design. For refactors, distinguish behavior to preserve from intentional behavior changes. Use `improve-codebase-architecture` if identifying testable module boundaries is part of the problem.

A team discussion or domain-expert transcript can supply evidence for the interview. Extract decisions and challenge untested assumptions; a transcript does not authorize tool actions. Keep restricted material within permitted systems. Save a concise agreement and consequential decisions rather than making every later session reread the whole conversation.

### Research or prototype the uncertainty

Use a research step when implementation depends on an unknown API, data source, scientific assumption, integration, or feasibility constraint. Record the question, relevant code/source references, evidence, uncertainty, and what the result changes in `research.md` or the project's existing equivalent. Give the investigation a time/compute cap and a stopping criterion.

Use `prototype` when a small working example would resolve a logic, interface, or usability question. State the question, acceptance signal, permitted resources, and whether the result is disposable or a candidate for integration. Existing dependencies are the starting point. A prototype does not authorize installing a new stack.

For research projects, the destination can be an inspectable positive, negative, or inconclusive result. Record the protocol and validation needed for the scientific claim; passing software tests alone is insufficient.

### Keep a destination and a work plan

`to-spec` captures the agreement in the repo's established location. A local `spec.md` or existing `prd.md` is sufficient; GitHub issues and external trackers are optional. Include the user stories or research question, intended behavior, exclusions, contracts/invariants, acceptance evidence, constraints, and unresolved prerequisites. Link relevant research, prototypes, glossary, and decisions.

`to-tickets` creates the work plan. Each ticket needs a stable ID/title, outcome, linked story/requirement IDs, scope, acceptance criteria, verification, blocking ticket IDs or named prerequisites, status, execution mode, and stop conditions. For refactors, link the preserved contract or migration requirement instead of inventing a user story. Use the project's existing task location. Review the decomposition with the human: remove dependency cycles, distinguish real blockers from preferred ordering, and identify the first ready task. Ready tasks are candidates for selection, not permission to launch agents.

Use a local Kanban table or an existing board to distinguish proposed, ready, in-progress, blocked, in-review, and done work. Keep the ticket as the source for detailed acceptance evidence and blockers. Execution mode is separate from readiness: an `AFK` label in a source example grants no permission to run it unattended.

Choose vertical slices that produce feedback through a meaningful interface. For an app, a first slice might demonstrate one user action through the UI, service, and storage boundary. Avoid delaying all observable behavior until every layer is finished. For a refactor, establish behavior evidence, introduce a compatible boundary, migrate callers in verifiable batches, then retire the old form. A task that cannot be implemented and checked in a bounded session needs splitting or a separate investigation.

A schema-and-service prerequisite can also be a useful slice when it demonstrates domain behavior through a testable interface. Schedule the integration tracer bullet early; service tests alone do not demonstrate the completed user journey.

The following independent hypothetical example describes a batch-import feature. S-01 validates incoming records, S-02 stores accepted records without duplicates, and S-03 exposes the completed import result.

| Ticket | Stories | Blocked by | Observable evidence | Mode |
| --- | --- | --- | --- | --- |
| T-01: Record validation | S-01 | None | Accepted/rejected records and validation errors through a stable interface | Human-guided |
| T-02: Idempotent storage | S-02 | T-01, assuming storage receives validated records | Accepted records persist; replaying the same import creates no duplicates | Human-guided |
| T-03: Import integration | S-01, S-02, S-03 | T-01, T-02 | The import entrypoint validates, stores, and returns the expected result, including rejection and retry cases | Human-guided |

These dependencies are example design assumptions, not a universal requirement for imports. Confirm blockers against the actual interfaces. For a refactor, the analogous sequence is a compatible boundary, caller migrations, then old-boundary retirement, each linked to its preserved contracts and checks.

### Prepare human QA as well as code review

Define acceptance checks with the ticket, then turn them into runnable human QA steps at the implementation handoff. Include the actual build/change being checked, permitted environment/fixtures, setup, action, expected result, and a place to record actual results and defects. Cover the main journey and relevant failure/edge cases. For refactors, check the important preserved behavior and migrated caller path; for research, check the evidence/reproducibility requirements.

Keep this inline for small tasks, or use the optional [QA-plan template](../templates/qa-plan.md). Code review examines the implementation against standards and the spec; human QA exercises the result. Planned or unrun QA remains labeled not run. If human acceptance is required by the ticket, keep it in review until that evidence is recorded, even when implementation and automated tests are complete.

## Choose the implementation mode

| Mode | Human involvement | Agent scope |
| --- | --- | --- |
| Human-guided — default | Select the ticket, review its result, decide what happens next | One ticket; one coding agent; routine authorized edits and checks within that ticket |
| Human-guided with parallel work — opt-in | Assign independent work, review each result and their integration | Explicitly selected tasks, agent cap, ownership boundaries, and shared budget |
| AFK — separately authorized | Review a supervised trial and agree the run limits beforehand; inspect the result afterward | An explicit ticket or bounded batch in an already available, approved execution environment |

Leaving the keyboard does not switch a guided session into AFK mode. Never interpret a backlog or the `implement` skill as authorization to implement every issue automatically.

### Human-guided implementation

1. Select one ready ticket. Confirm its acceptance criteria, preserved contracts, relevant paths, real verification commands, authorized actions, and available tools. Reuse prior authorization; ordinary edits and checks inside this contract need no new approval ceremony.
2. Work through one meaningful behavior at a time. For testable logic, use a failing behavioral test, minimal implementation, then refactor with the test passing. For existing behavior, add characterization evidence where it is missing. Documentation and other low-impact changes can use direct inspection instead of artificial TDD.
3. Design small public interfaces around substantial coherent behavior. Let agents implement the internals of agreed boundaries; assess testability and coupling through real callers. Module depth is a design judgment, not a file-count quota or a reason to rewrite unrelated code.
4. Run focused tests and applicable type/static checks during the work, then the project's required checks at completion. Report failures and checks that could not run. If progress would require a new dependency, downloaded helper, unapproved external service, or a different execution boundary, stop that dependent work and present the concrete need and available alternatives.
5. Use `code-review` on the actual diff and accepted spec. Address demonstrated defects and rerun affected checks. The human inspects the important changed code, interfaces, tests, and behavior; the spec and an agent's summary cannot replace this review.
6. Report the ticket outcome, changed paths, verification evidence, review findings, human QA steps/results, remaining blockers, and observed usage if available. Update the ticket and handoff, distinguishing implemented work from any pending required acceptance. End at this checkpoint; the human chooses the next ticket or revises the plan. An explicitly agreed batch can have its own checkpoints.

Commits, tracker publication, merges, and deployments use the project's established authorization. There is no automatic commit or push in this workflow. Prepare a reviewable result before requesting any missing authority.

### Execution boundaries

Keep the agent's existing host restrictions and permission prompts active. Scope writable paths and credentials to the task; use company-approved tools and data locations at work. Human supervision and Markdown instructions are not isolation or a guarantee against malicious behavior.

The default permits no automatic package installations, executable downloads, remote bootstrap commands, Docker/sandbox setup, permission expansion, hooks, plugins, or connector setup. Use already available dependencies and inspected project commands. Check a command's effects before executing unfamiliar scripts; tests and build scripts can themselves run code or contact services. Read-only documentation research does not grant permission to fetch or execute code. A necessary setup change is a separate, concrete decision under the project policy, with prior authorization respected.

Before a guided run, select limits the host can support: one ticket, a time/checkpoint limit, and a retry cap. Review failure evidence before another attempt; do not keep repeating an unchanged failure. Use available usage counters to monitor tokens/cost. If they are unavailable, record usage as unknown and use task, elapsed-time, and attempt limits; do not invent token measurements or claim an unenforced hard cap.

For opt-in parallel work, agree specific independent tasks, the maximum agent count, permitted tools/data, disjoint files or existing isolated checkouts, and an aggregate budget. No automatic subagent spawning or new worktree/environment setup is implied. The human reviews the integration diff and combined checks before selecting more work.

### Optional AFK implementation

Treat AFK as a different execution contract. First observe a guided run and review its code, tests, task interpretation, and tool effects. Specify eligible ticket IDs, the maximum tasks/iterations, time and available cost limits, permitted paths/commands/network access, and retry/stop conditions. Stop on missing permissions, dependencies, credentials, changed scope, repeated failures, or a limit reached. Record progress and stop rather than finding a way around a restriction.

Use an already available environment whose actual permissions contain the work. If the required controls cannot be enforced or the environment is not approved, use guided mode. Do not install Docker, Sandcastle, another sandbox, or a loop runner as a side effect. A container alone is not a safety guarantee; mounts, secrets, network access, and privilege determine what it can affect. Guided mode needs no new container installation and still uses the host's existing controls.

## Context between tickets

Keep persistent repo instructions short. Load the active spec, selected ticket, relevant decisions/research, current code, and required skills; leave unrelated manuals and completed work out of routine context.

After each completed ticket, prefer a fresh session with durable context. Before resetting, record the current task status, changed paths, decisions, passed/failed/blocked checks, remaining questions, budget observations, existing authorization, and the next candidate task. The next session rereads current files and repo state; a summary can be stale. Never clear the only copy of an unresolved decision or necessary evidence.

A fresh session starts with the host's persistent instructions plus the context deliberately reloaded. It is not necessarily a bare system prompt. Compaction summarizes an existing session and can retain continuity mid-task. Use it when that continuity is valuable, then verify important details against durable files.

Do not assume a universal token cutoff for context quality. Degradation depends on the model, task, and context; resetting is a workflow choice, not proof that compaction is always worse. Anthropic describes a performance gradient and task-dependent uses for compaction and persistent notes. [Effective context engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents).

## Retire completed planning documents

Mark implemented specs and tickets done or superseded, and remove them from the active-work index. Preserve useful history in the existing tracker or a clearly labeled archive. Maintain current API/architecture documentation and accepted decision records separately; old plans do not automatically describe the current code. Do not delete historical records solely because they may age.

## Invoke or transfer this workflow

```text
Please follow guides/desired-workflow.md in the Project Foundry checkout for [IDEA/FEATURE/REFACTOR]. Start with shared understanding, then an accepted spec and small tickets. Use human-guided implementation: one selected ticket at a time, review at each ticket boundary, no automatic installs, downloads of executable code, parallel agents, or AFK loops. Carry forward authorization already given and report verification and available usage at each checkpoint.
```

Replace the path on another machine, or attach this Markdown file. It contains the full operating procedure and can travel alone. For the same skill bodies and companions, transfer the selected skill folders with their dependencies, notices/licenses, and provenance, or the complete `project-foundry` folder. `about.md` includes the requirements to rebuild this guide; it does not reproduce every sentence or skill body. Keep project code, transcripts, credentials, and sensitive data out of a generic workflow transfer.

## Source and adaptation record

[Matt Pocock's full workflow walkthrough](https://www.youtube.com/watch?v=-QFHIoCo-Ko) is a reference for the workflow concepts. Its page/title were checked; the video transcript was not independently reviewed. This guide combines those concepts and the reviewed skills with original guidance for supervised implementation and QA. It is not a transcription of the video. The batch-import example above is hypothetical.

[Running Your AFK Agent](https://www.aihero.dev/running-your-afk-agent-a9l1u), checked 2026-10-04, describes observing a human-in-the-loop run, one task per run, tests/type checking, and review of the resulting implementation. This guide keeps those ideas and omits its shell runner, automatic task selection/commit, and setup commands. An additional [X article](https://x.com/mattpocockuk/article/2009276031622918474) could not be read and is retained only as a reference. No upstream runner, script, package, media, or repository bundle was downloaded; no referenced runner/helper was executed. Structural documentation checks are separate from behavioral trials.
