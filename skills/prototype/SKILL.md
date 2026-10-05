---
name: prototype
description: "Build a bounded throwaway prototype to answer a logic, state-model, or UI design question before implementing the maintained solution."
---

# Answer a design question

State the question and what observation would settle it. Reuse task constraints and set a time/compute cap. Choose [LOGIC.md](LOGIC.md) for state/data behavior or [UI.md](UI.md) for competing interface layouts; load only that branch. Numerical or scientific feasibility experiments use the project's research workflow rather than forcing an HTML demo.

Label prototype artifacts and keep them in an existing development/scratch location. Use the project's existing tools or a self-contained local demo; adding dependencies or services is outside this workflow. Default to synthetic/in-memory data and stubbed mutations. A persistence question needs an explicitly permitted scratch store, not a production connection.

Include checks needed to answer the question reliably; defer unrelated production hardening. Prototype evidence does not replace release gates. Record the verdict, observations, limitations, and artifact path when the question is settled or the cap is reached.

Keep the evidence locally using project conventions. Branch creation, commits, tracker writes, and publication are separate actions, not automatic cleanup steps. Promote a validated decision through normal implementation and verification; do not treat the prototype as production-ready code.
