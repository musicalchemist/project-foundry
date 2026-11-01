# Evidence that the work is correct

Choose checks from the behavior, invariants, uncertainty, and failure consequences. Match the test level to the property being verified. Tests, type checks, manual inspection, evaluations, and scientific validation answer different questions.

| Concern | Useful evidence |
| --- | --- |
| Domain behavior | Unit/property tests through stable interfaces |
| Database/service boundaries | Integration and contract tests |
| Main user journey | A few end-to-end tests or repeatable acceptance checks |
| Authorization | Cross-user/cross-tenant denial and privilege-boundary tests |
| UI changes | Running UI inspection, keyboard/accessibility checks, relevant screenshots |
| Numerical calculations | Known cases, invariants, reference calculations, tolerances and edge cases |
| Scientific inference | Design/sampling checks, sensitivity analysis, uncertainty, independent validation |
| ML/LLM behavior | Held-out evaluation, subgroup/error analysis, cost/latency and robustness |
| Operation | Smoke checks, restore drills, alert routing, migration/recovery rehearsal |

## During development

For a bug, reproduce failure before fixing it when practical. For logic with clear inputs and outputs, use red-green-refactor: a test fails for the intended reason, the smallest implementation passes, then improve the design. Work in vertical slices. Do not write a large batch of tests for an imagined API before learning from implementation.

Tests should assert observable contracts and important invariants. Prefer deterministic inputs and control time/randomness. Use real integration boundaries when mocks would conceal the risk. Avoid tests that merely repeat the code, inspect private implementation details, or approve generated snapshots without review.

Run the relevant fast checks during iteration and broader required checks before delivery. Formatting-only or documentation edits often need no new test. Check links, commands, or rendered output when those are the actual behavior. Do not repeat an unchanged expensive suite after it passed unless a new concern justifies it.

## Human QA and acceptance

When human acceptance is needed, turn the ticket's criteria into steps for the actual build or artifact: permitted environment/fixtures, actions, observable expected results, and recorded actual results. Include affected failure cases and preserved behavior for refactors. The [QA-plan template](../templates/qa-plan.md) provides this structure; small tasks can keep it inline.

Code review checks the implementation; human QA exercises the result. A drafted plan is not evidence of passing checks. Record passed, failed, blocked, and not-run checks separately, and keep a ticket in review while required acceptance is pending. Use existing approved setup; drafting QA steps does not authorize installing tools or affecting production.

## Honest reporting

Record the command, environment, result, and relevant scope. Distinguish passed, failed, blocked, and not run. Existing failures need triage; do not disguise them as success or silently broaden the assignment. A passing build establishes compilation, not product correctness. A passing notebook establishes execution, not causal validity.

For nondeterministic models or concurrency, evaluate repeated trials when meaningful and report the distribution. Keep thresholds tied to requirements and baseline behavior. Do not tune to the held-out set and continue calling it independent evaluation.

## CI as repeatable evidence

Prefer one documented command per check that works locally and in CI. Use locked dependencies and representative, permitted fixtures. Keep ordinary PR checks fast. Put expensive training, broad model evals, hardware-specific tests, and long research reruns in a separately scoped pipeline with budgets and artifacts. Fail releases on defined hard blockers; document accepted residual risks with an owner.

When CI is flaky, identify the source and owner. Retry only with a reason; quarantine with an expiry if needed. Repeated reruns until green conceal failure modes.
