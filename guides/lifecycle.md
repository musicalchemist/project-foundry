# Adaptive development lifecycle

A project progresses through decisions supported by evidence. Stages can overlap; uncertainty can send work back to discovery. Keep the artifact size proportional to what needs to be communicated.

| Stage | Decision and useful artifact | Exit evidence |
| --- | --- | --- |
| Discover | Problem/research question, audience, alternatives; brief | A specific need or question and a way to assess success |
| Test feasibility | Data access, technical spike, baseline, cost estimate | Hardest prerequisite tested or a named unresolved blocker |
| Scope | First useful result, exclusions, acceptance criteria | A small result deliverable with available resources |
| Design | Boundaries, data flow, failure behavior; ADR if consequential | Interfaces and tradeoffs sufficient for the first slice |
| Plan | Milestones and dependency-ordered tasks | Each task has an outcome, verification, and prerequisites |
| Build | One vertical slice, reviewable diff | Behavior works through its real interface; relevant checks pass |
| Validate | User/scientific acceptance and quality checks | Evidence supports the intended claim and limitations are recorded |
| Release/share | Versioned artifact, reproducible run or release plan | Identified artifact, destination, owner, and applicable recovery path |
| Operate | Telemetry, maintenance, response, periodic review | Signals reach an accountable owner; failure/recovery paths work |
| Retire | End service/data/model life deliberately | Users informed as authorized, access revoked, retention fulfilled |

## Rigor by maturity and consequence

Explore: one short brief, a bounded experiment, a representative check, and a result record can suffice. Avoid building deployment machinery for work you will discard. Keep secrets and sensitive data controlled at this tier.

Build: use reproducible environments, meaningful tests, stable interfaces, and lightweight design records. Shared research also needs protocols, lineage, and reproducible outputs. A maintained internal tool belongs here even with few users.

Operate: add CI/release gates, security boundaries, monitoring, budgets, backups, incident ownership, and verified recovery. Consequential applications may need specialist, organizational, or regulatory review based on their actual use.

## Planning that survives feedback

Keep near-term tasks detailed and later milestones coarse. Identify dependencies, riskiest assumptions, and critical-path constraints. Estimate ranges from known work and comparable experience; label speculative estimates. For research, milestones may be evidence decisions rather than feature deliveries.

Use a short work queue: current task, next few ready tasks, blocked items, and deferred scope. Limit simultaneous work to what can be reviewed. A completed milestone produces a demo, evidence bundle, or reproducible result. Record what changed and revise the remaining roadmap when evidence changes.

For an existing repo, inspect its structure, real commands, tests, deployment conventions, and user changes first. A quick bug fix needs reproduction, correction, regression evidence, and a handoff; it need not restart the whole lifecycle.

## Done and ready

A task is ready when its behavior/question, scope, prerequisites, and verification are clear enough to work. It is done when the result meets the acceptance criteria, relevant checks ran, review concerns are resolved or recorded, and the next person can use or reproduce it.

Research can be done with a well-supported negative or inconclusive result. Successful code execution alone does not validate the scientific claim. A product can be implemented but still fail user acceptance. Track these separately.
