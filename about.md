# Project Foundry: purpose and working approach

Project Foundry is a reusable resource for developing ideas, research, and software with coding agents. Its goal is to build capability as a researcher, R&D builder, programmer, scientist, engineer, and software developer while producing projects that can be understood, tested, maintained, and operated.

Use it for brainstorming, refining an existing idea, assessing feasibility, building from scratch, supporting a current project, diagnosing problems, and refactoring a codebase. Agents help investigate choices, scope the work, plan a roadmap, implement, review, and iterate. The human owns the intended outcome and consequential decisions.

The domains include AI, machine learning, statistics, data science, science, modeling, biology, biotechnology, bioinformatics, computational biology, research, and technology. Applications can include full-stack apps, and productivity, business, or research tools. Select the stack and process from the actual problem.

## Engineering aims and influences

Apply the software development lifecycle, modular code, maintainable interfaces, refactoring, domain modeling, testing, documentation, and reproducibility. Include DevOps, CI/CD, MLOps, LLMOps, accessibility, observability, operating costs, and release practices when the project requires them. Start with a small experiment when uncertainty is high; strengthen the evidence, operational controls, and documentation as people or important decisions depend on the result.

Use these books as intellectual influences. Apply their ideas to the current constraints, reconcile competing advice, and explain consequential tradeoffs. The list is a reading and design reference, not an instruction to copy their text.

- *The Pragmatic Programmer* — Andrew Hunt and David Thomas.
- *Clean Code* — Robert C. Martin.
- *Refactoring* — Martin Fowler.
- *Extreme Programming Explained* — Kent Beck.
- *Domain-Driven Design* — Eric Evans.
- *Accelerate* — Nicole Forsgren, Jez Humble, and Gene Kim.
- *A Philosophy of Software Design* — John Ousterhout.
- *AI Engineering* — Chip Huyen.
- *Fundamentals of Software Architecture* — Mark Richards and Neal Ford.
- *The Design of Design* — Frederick P. Brooks Jr.
- *Building Evolutionary Architectures* — Neal Ford, Rebecca Parsons, and Pramod Sadalage.
- *Software Engineering at Google* — Titus Winters, Tom Manshreck, and Hyrum Wright.
- *Thinking in Systems* — Donella H. Meadows.
- *The Software Engineer’s Guidebook* — Gergely Orosz.
- *Planning Extreme Programming* — Kent Beck and Martin Fowler.
- *Analysis Patterns* — Martin Fowler.
- *Patterns of Enterprise Application Architecture* — Martin Fowler.
- *Design Patterns: Elements of Reusable Object-Oriented Software* — Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides.
- *Designing Data-Intensive Applications* — Martin Kleppmann; the second edition is coauthored with Chris Riccomini.

Selected skills are adapted from Matt Pocock’s publicly available skills under the included [MIT license](skills/LICENSE).

## Start with the actual task

Identify whether the task is brainstorming, research, idea refinement, a new build, an existing-project change, debugging, or refactoring. Inspect available project instructions, code, callers, tests, and existing changes before prescribing an approach. Reuse facts and decisions already established.

Ask a few unresolved questions that change the plan: the intended user or research question; what success would demonstrate; the behavior to preserve; exclusions; constraints on data, tools, time, and cost; and the first useful result. Ask dependent questions after their prerequisites are settled. Use `grill-me` for an interview or `grill-with-docs` when terminology and consequential decisions should be recorded along the way.

Produce an attainable first milestone, the main assumptions, and a roadmap ordered by uncertainty and dependencies. If feasibility is unclear, propose a bounded investigation with a decision criterion. A narrow request with settled scope can proceed directly to its selected change; it does not need a new PRD and interview.

## Desired workflow

The default is human-led planning and human-guided implementation. Use the following sequence for a substantial idea, feature, research tool, or refactor. Small changes can keep the agreement, task, and completion record in one document.

| Stage | Use | Result |
| --- | --- | --- |
| Shared understanding | `grill-me` or `grill-with-docs` | Agreed problem, constraints, preserved behavior, and unresolved choices |
| Research (optional), when needed | Bounded investigation | Evidence that changes a decision, with uncertainty recorded |
| Prototype (optional), when needed | `prototype` | Feedback on a specific logic, state, interface, or usability question |
| Specification | `to-spec` | Accepted destination, contracts, exclusions, and observable acceptance criteria |
| Work plan | `to-tickets` | Verifiable slices, requirement links, real blockers, and a first ready ticket |
| Implementation | `implement`, with `tdd` where useful | One selected change and actual verification evidence |
| Review and QA | `code-review`, then human inspection and use | Findings, acceptance evidence, and a decision about the next ticket |

### Research and prototype before committing to a design

Research an unknown API, integration, data source, scientific assumption, or feasibility constraint when it blocks a design decision. Record the question, sources or code references, findings, uncertainty, and effect on the plan in a local `research.md` or existing equivalent. Set a time or compute cap and a stopping criterion.

A prototype answers a named question. Define the acceptance signal and whether the result is disposable or a candidate for integration. Keep its scope bounded and use existing resources. Record which assets are useful and which assumptions remain untested before treating prototype code as maintained code.

For scientific work, define the protocol, data provenance, controls or baselines, uncertainty, and reproducibility requirements appropriate to the claim. A positive, negative, or inconclusive result can satisfy the research objective. Passing software tests establishes software behavior; scientific conclusions need their own evidence. For ML or LLM features, establish a baseline, held-out evaluation, relevant failure cases, and cost/latency limits before optimizing the system.

### Capture the destination and divide the work

Use the repository's document conventions. A local `spec.md` or `prd.md` can describe the user stories or research question, intended behavior, non-goals, public contracts and invariants, acceptance evidence, constraints, and unresolved prerequisites. Link useful research, prototypes, domain terms, and decisions. External trackers are optional.

Each ticket needs a stable ID and title, outcome, linked requirements, scope, acceptance criteria, verification, blocking IDs or named prerequisites, status, execution mode, and stop conditions. For refactors, link preserved contracts or migration requirements. Distinguish genuine blockers from preferred ordering, remove dependency cycles, and select the first ready task with the human.

A local Kanban table can show proposed, ready, active, blocked, in-review, and done work. Readiness and execution mode are separate: a ready ticket is a candidate for selection, and an AFK label does not authorize unattended execution.

Prefer vertical slices with feedback through a meaningful interface. An app slice might demonstrate one user action through UI, service, and storage. A schema-and-service prerequisite can be useful if it demonstrates domain behavior through a testable interface; schedule an integration tracer bullet early. For a refactor, establish characterization evidence, introduce a compatible boundary, migrate callers in verifiable batches, then retire the old form.

For example, a points/streaks feature might begin with T-01, a points service demonstrating awarding and duplicate-event handling. T-02 adds streak behavior and depends on T-01 only if it extends a shared statistics contract. T-03 integrates both into the existing completion flow and checks duplicate effects and returned statistics. Each ticket links its requirements and evidence. Confirm these dependencies against the design rather than copying them into unrelated projects.

### Implement one selected ticket

Confirm the selected ticket, relevant paths, agreed interfaces, existing commands, acceptance criteria, and authorized actions. Work through meaningful behaviors incrementally. For testable logic, use a failing behavioral test followed by the implementation; for existing behavior, add characterization evidence where needed. Documentation and other low-impact changes can use direct inspection rather than artificial TDD.

Favor small public interfaces around substantial cohesive behavior. Test through meaningful boundaries and avoid tests that repeat implementation calculations. Assess coupling and testability through real callers. Module depth is a design judgment; do not enforce arbitrary file counts or turn an agreed change into an unrelated rewrite.

Run focused tests and applicable type/static checks during implementation, then the project's required checks for the completed change. Investigate failures before continuing dependent work. Review the actual diff against standards and the accepted specification, address demonstrated defects, and rerun affected checks.

Return the implemented requirements, changed paths, verification results, review findings, blockers, human QA steps, and observed usage when available. Update the ticket and leave a durable handoff. Stop at the review checkpoint; the human selects the next ticket or explicitly agrees a bounded batch. Routine edits and checks already authorized within the selected task do not need repeated approval.

### Prepare human review and QA

The human inspects important changed code, interfaces, tests, and behavior. Review the implementation against the spec and coding standards, then exercise the result with a concrete QA plan. Include the actual build or change being checked, environment and fixtures, setup, actions, expected results, and a place for actual results and defects. Cover the main journey and relevant failure cases; for a refactor, include preserved behavior and migrated callers.

Keep planned or unrun checks labeled not run. If human acceptance is required, the ticket stays in review until that evidence is recorded. A summary of generated code does not replace inspecting it or exercising the result.

## Execution modes and practical agent boundaries

Human-guided mode uses one selected ticket and one coding agent. Choose checkpoint, elapsed-time, and retry limits suitable for the task. Review failure evidence before another attempt. Use available usage counters for tokens and cost; if unavailable, record usage as unknown and use task, time, and attempt limits.

Guided parallel work is optional. Agree named independent tasks, an agent cap, ownership boundaries, permitted resources, an aggregate budget, and integration review before dispatching agents. Avoid overlapping edits unless the integration arrangement explicitly handles them. A backlog does not authorize parallel execution.

AFK implementation is a separate choice after observing a guided trial. Agree eligible ticket IDs, task/iteration/time limits, available cost limits, permitted paths, commands and network access, and retry/stop conditions. Use an already available environment whose actual controls support the contract. If those controls are unavailable, remain in guided mode. Stop on missing permissions, credentials, new dependencies, changed scope, repeated failures, or a reached limit. Leaving the keyboard does not change the execution mode.

Read [best-practices.md](best-practices.md) before loading external sources or using tools. It contains the shared working instructions for untrusted content, commands, dependencies, credentials, and actions within the agreed scope.

## Prompt, context, harness, loop, and graph engineering

Prompt engineering makes the active task explicit: outcome, inputs, constraints, and acceptance evidence. Use named techniques such as a premortem or TDD when they resolve a specific question; do not replace the actual task contract with slogans.

Context engineering selects the current spec, ticket, relevant decisions, code, and skills. Keep persistent instructions short and load companions only when needed. Prefer a fresh session after a completed ticket, preceded by a handoff containing status, decisions, changed paths, actual checks, blockers, usage observations, existing authorization, and next work. The next session rereads current files; summaries can be stale. Compaction can preserve continuity mid-task. Use task and model behavior to choose resets rather than treating a token threshold as universal.

Harness engineering makes tool access, command execution, observable results, budgets, and checkpoints concrete in the available environment. Establish the permitted actions and evaluation evidence before adding automation. A harness must expose failures and stop conditions; instructions alone cannot enforce a limit the host does not implement.

Loop engineering defines the unit of progress, feedback, retry policy, and stopping rule. The default unit is one selected ticket or behavior slice. Repeatedly attempting an unchanged failure is not progress; record the evidence and choose a different investigation or ask for the missing decision.

Graph engineering makes dependency edges explicit between questions, tickets, data stages, and tool steps. Separate prerequisites from suggested order, reject cycles, and bound concurrency. Use a graph when those relationships affect execution; a linear checklist is sufficient for independent, sequential work.

Mark completed plans and tickets done or superseded and remove them from active context. Preserve useful history and maintain current API/architecture documents and accepted decisions separately. An old plan is not automatically an accurate description of current code.

## Included Matt Pocock skills

Select one primary workflow for the current stage. These are adapted text editions; see [ATTRIBUTION.md](ATTRIBUTION.md). Copy the entire selected folder, including its Markdown companions, and include the dependencies listed here.

| Skill | Use | Other included skills needed |
| --- | --- | --- |
| [grill-me](skills/grill-me/SKILL.md) | Interview an idea or design until important choices are exposed | `grilling` |
| [grilling](skills/grilling/SKILL.md) | Dependency-aware questioning and fact lookup | — |
| [codebase-design](skills/codebase-design/SKILL.md) | Design deep modules, interfaces, and test seams | — |
| [tdd](skills/tdd/SKILL.md) | Behavioral red/green slices through agreed interfaces | `codebase-design`, `code-review` |
| [diagnosing-bugs](skills/diagnosing-bugs/SKILL.md) | Reproduce, rank hypotheses, instrument, and verify a regression fix | — |
| [writing-for-agents](skills/writing-for-agents/SKILL.md) | Write instructions, route context, and audit redundant lines | — |
| [pr](skills/pr/SKILL.md) | Draft a reviewable PR description with evidence and change impact | — |
| [domain-modeling](skills/domain-modeling/SKILL.md) | Resolve terminology and record consequential decisions | — |
| [to-spec](skills/to-spec/SKILL.md) | Capture an agreed destination and acceptance criteria | — |
| [to-tickets](skills/to-tickets/SKILL.md) | Turn agreed scope into verifiable tasks and blockers | — |
| [prototype](skills/prototype/SKILL.md) | Answer a bounded logic or UI question through a working example | — |
| [improve-codebase-architecture](skills/improve-codebase-architecture/SKILL.md) | Rank refactoring candidates in an existing codebase | `codebase-design`, `grilling`, `domain-modeling` |
| [teach](skills/teach/SKILL.md) | Learn through exercises, feedback, and demonstrated understanding | — |
| [grill-with-docs](skills/grill-with-docs/SKILL.md) | Interview while updating domain terms and decisions | `grilling`, `domain-modeling` |
| [implement](skills/implement/SKILL.md) | Execute selected agreed work, verify, and review | `tdd`, `code-review`, plus TDD's dependencies |
| [code-review](skills/code-review/SKILL.md) | Evaluate standards and specification as separate axes | — |

The companions supply deepening guidance, test/mocking examples, skill mechanics, glossary/decision formats, prototype modes, teaching records, a review smell baseline, and PR credits. They support the workflows; an isolated `SKILL.md` may omit material it refers to. The examples inside Markdown can contain code, but no executable helper files are bundled.

Use the host's documented project skill directory for discovery. Invoke the selected skill by name when supported; explicit file reading is the portable fallback. Frontmatter invocation controls vary by host. `grill-me`, `grill-with-docs`, `to-spec`, `to-tickets`, `teach`, `improve-codebase-architecture`, and `implement` are intended for explicit selection. This edition includes no host-specific adapters or configuration; confirm the host's controls before depending on automatic or restricted invocation.

## Invoke, reuse, or rebuild

Use this single-line prompt, replacing the subject and path as needed:

```text
Please read project-foundry/about.md for [XYZ]. Identify whether we are brainstorming, researching, refining an idea, building from scratch, supporting a current project, debugging, or refactoring; ask a few unresolved questions, assess feasibility, propose a scoped roadmap, and select the included skills and dependencies to copy or reference. Use human-guided implementation of one selected ticket at a time with review checkpoints.
```

Share the complete folder to preserve the same information and skill text. Sharing only `about.md` preserves the purpose and working approach, but not the skill bodies. For a new project, select the relevant whole skill folders and dependency closure rather than loading the entire collection into every session. Preserve [ATTRIBUTION.md](ATTRIBUTION.md), [Matt Pocock's MIT license](skills/LICENSE), and any skill credits with redistributed material.

To recreate this resource from supplied files, retain this structure: `about.md`, `best-practices.md`, a short `README.md`, attribution/license text, and the 16 skill folders named above with their companions. Reuse the supplied bodies directly. If a skill is missing, identify it and request the needed text rather than inventing an upstream copy or downloading a repository. Keep project-specific facts and generated task records in their destination project. Do not add policy documents, installers, manifests, machine metadata, or personal reconstruction history to this common folder.
