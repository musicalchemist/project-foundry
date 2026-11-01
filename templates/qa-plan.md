# Human QA and acceptance plan

Customize for the selected ticket and actual environment. Keep checks inline in a small task if a separate file adds no value. Drafting this plan does not authorize setup, installations, external access, production changes, or claim any check ran.

- Ticket IDs and linked spec/story/requirement IDs:
- Build, commit/change set, or research artifact/version under review:
- Reviewer and required acceptance owner:
- Permitted environment, existing commands, and safe fixtures/accounts/data:
- Setup and cleanup, including any unmet prerequisite:
- Automated verification and code-review evidence already available:
- Required human checks versus optional checks:

## Acceptance checks

Replace the placeholder row with relevant checks. Include the main user journey or reproducibility check, affected edge/failure cases, and preserved behavior for a refactor. State observable expected results before recording actual results.

| Check / requirement ID | Setup and actions | Expected result | Actual result / evidence | Status |
| --- | --- | --- | --- | --- |
| Replace with a scoped check | Exact steps using permitted resources | Observable criterion | Leave blank until run | not run |

Use `passed`, `failed`, `blocked`, or `not run`. An agent may draft the plan and report checks it actually performed; human checks need evidence from the reviewer. Record unavailable environments or data as blockers rather than inventing results.

## Acceptance decision

- Defects: check ID, reproduction, expected/actual behavior, impact, and follow-up ticket:
- Required checks still failed, blocked, or not run:
- Reviewer decision: accepted | changes required | pending:
- Explicitly accepted limitations and owner, if applicable:
- Next action and ticket status:

An implemented ticket with pending required acceptance stays in review. Mark it done when its agreed completion evidence is satisfied; optional unrun checks remain visible as limitations.
