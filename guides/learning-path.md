# Build professional competence through projects

Use coding agents to accelerate practice while retaining responsibility for understanding the result. Choose one main project and finish usable increments. Reading becomes more valuable when connected to a design choice, observed failure, or code review.

## A project sequence

| Stage | Practice project | Demonstrate before moving on |
| --- | --- | --- |
| Foundations | CLI tool or reproducible analysis package | Explain the code; use Git, environments, types, tests, debugging, and basic data structures |
| Maintainable application | Small app with storage and one useful journey | Modular design, migrations, input validation, auth if needed, CI, documentation |
| Operated service | Deploy the app to a suitable environment | Logs/metrics, alert owner, backups/restore, release/recovery, costs, security boundaries |
| Scientific/ML system | Public-data study or prediction pipeline | Protocol, lineage, leakage-safe splits, baseline, uncertainty, rerunnable outputs |
| Evaluated LLM system | Bounded assistant with a real task set | Eval cases, retrieval/tool authorization, failure tests, cost/latency caps, versioned prompts |
| Independent project | A domain problem with users or a scientific audience | Scope choices, evidence-driven changes, external review, maintenance and clear limits |

Use dates only after matching scope to your weekly availability. A suggested first cycle is to choose a small problem, ship one tested vertical slice, obtain user or domain feedback, and improve it. Increase scale after demonstrating the preceding competencies. A broad portfolio develops over sustained projects; one resource cannot replace practice or expert review.

## Work with an agent without losing the skill

Before a change, predict the approach or write the intended behavior. Ask the agent to explain tradeoffs and point to the code or source behind its claims. Read the diff and reproduce key checks. Reimplement a small component without the agent periodically. Diagnose at least some bugs yourself before comparing methods.

For research, independently inspect data, sampling, assumptions, and a small reference calculation. For generated code, explain the interfaces, failure behavior, authorization, and deployment path. If you cannot explain a critical component, narrow it or study it before relying on it.

## Study by current need

Start with *The Pragmatic Programmer*, *A Philosophy of Software Design*, and *Refactoring* alongside small projects. Use XP and planning books for short feedback cycles. Add domain modeling and architecture books when boundaries and competing requirements become concrete. Study *Designing Data-Intensive Applications* when persistence/distribution choices arise, *Accelerate* when operating delivery systems, and *AI Engineering* when evaluation and AI deployment become central.

Read *Clean Code* and design-pattern books critically: naming and coherent responsibilities help, while mechanical rules or pattern-heavy code can obscure the problem. Research work also needs statistical design, numerical methods, domain literature, and methods review beyond the software books listed here.

## Evidence of growth

Keep a small portfolio of code, reproducible results, ADRs, reviews, and lessons from failures. Track accepted outcomes, defects caught before release, successful reproductions, time to recover, and cost where available. Use these to improve your workflow; avoid treating lines of code, number of agents, or hours of reading as competence measures.

End each milestone with one demonstrated lesson and one next skill to practice. Update shared guidance only when a lesson generalizes across projects.
