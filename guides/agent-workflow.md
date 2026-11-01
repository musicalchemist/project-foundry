# Working with coding agents

The agent should know the goal, relevant context, constraints, verification method, and authority to act. Keep project memory in durable files so the next session can continue without reconstructing a long chat.

For an idea-to-code or refactoring procedure, follow the [guided workflow](desired-workflow.md): human-led planning, human-guided implementation of one selected ticket, and review before the next ticket. It also defines opt-in parallel/AFK modes and fresh-session handoffs. Use the general guidance below within that selected mode.

## The working loop

1. Inspect trusted repo instructions, current changes, relevant code, and real commands.
2. State the intended result and resolve decisions that materially affect it. Small edits can proceed directly; unfamiliar or consequential work benefits from a plan.
3. Read targeted context and authoritative documentation for uncertain external behavior.
4. Implement the smallest useful slice and check its behavior.
5. Review the diff against the task and affected trust boundaries. Correct supported findings.
6. Record outcome, evidence, limitations, and the next useful step.

Use a compact task contract: goal, non-goals, relevant paths, behavior/acceptance criteria, verification, dependencies, and authorized actions. Avoid requiring a rigid role ceremony for every change. Keep humans responsible for scientific interpretation, major tradeoffs, risk acceptance, and authority to affect real systems.

Include relevant artifacts as paths: an existing spec, mockup, sample input/output, schema, or prior decision. Read only the parts needed for the task. For substantial uncertainty, a useful opening prompt is: “Work back and forth with me, starting with your open questions and outline before writing the plan.” Reuse settled answers; leave planning mode when implementation is authorized and the material decisions are resolved. Planning does not require another approval for each ordinary edit.

Use one primary workflow per stage. The original Foundry procedures and selected Matt workflows are alternatives or deliberate companions; do not stack multiple planning/review frameworks by default. Reuse the codebase's existing component, then a suitable platform/standard-library feature or installed dependency before proposing a new dependency. Keep validation, security, error handling, and accessibility proportional to the behavior even when the implementation is small.

## Context and usage efficiency

Keep `AGENTS.md` short and accurate: purpose, key boundaries, real commands, non-obvious constraints. Put optional procedures in skills and read them when triggered. Search before loading directories. Keep file/line references to evidence, summaries of decisions, and explicit uncertainty. Do not paste full logs, generated artifacts, or all manuals into the chat.

Use lower effort or cheaper available models for well-specified low-risk work only when their observed quality is sufficient. Use stronger reasoning for ambiguous design, difficult debugging, or consequential review. Do not encode a permanently preferred model; availability and performance change.

Set caps for uncertain searches, repeated attempts, paid calls, training, and long-running loops. Review failure evidence before retrying. Measure cost and time per accepted outcome when telemetry exists; do not invent token savings or claim access to counters the host does not expose.

Maintain one active task and a short queue. Checkpoint at decision and milestone boundaries, not after every tiny edit. A handoff records exact state, changed paths, decisions, checks, failures, unresolved questions, and next actions. Re-read current files after a handoff; summaries can be stale.

## Agent orchestration

One agent is usually enough for a coherent task. Parallel agents help when independent questions or isolated changes have clear contracts and reviewable outputs. Use them only within the user’s and host’s delegation permissions. Give each a narrow input, expected output, relevant evidence, and an ownership boundary. Separate worktrees or disjoint files reduce collisions. Review integration, interfaces, and combined tests before considering parallel work complete.

An independent review can catch mistakes, but two agents agreeing is not proof. Check their claims against behavior and evidence. Avoid circular review, sprawling role hierarchies, and full-history copies for every small subtask.

Review through the perspectives the change needs: product value and scope, architecture and failure behavior, UI/accessibility, real-user QA, security, and operation. These can be questions in one review rather than separate agents. Verify completion claims against current evidence; an agent's success report, a linter, and a passing behavioral check establish different things.

## Persistent quality

At completion, report what changed, why, what was verified, and material limits. Promote repeated, demonstrated lessons into concise repo rules or targeted skills. Remove obsolete lessons. Keep tool grants, hooks, and executable checks separate from prose guidance, with review of their real privileges.

Use [host setup](host-setup.md) for version-sensitive Codex/Claude behavior, [security tools](security-tools.md) when the task calls for security review, and [resource intake](resource-intake.md) for outside material. The [resource catalog](../references/resources.md) credits principles considered from Ponytail, Superpowers, gstack, and ECC; their runtimes are not required.
