# Choose security checks for the task

Keep the application's security controls, tests, dependency checks, secret detection, and CI alongside agent review. Neither a skill nor a scanner establishes that a change is safe. Record the target, actual coverage, evidence, failures, and unrun checks.

## Available native capabilities

Inspect the tools/skills actually exposed by the current host. When the task calls for security review, use the maintained native workflow if available and compatible with the authorized target and data policy. Do not copy the entire vendor skill library into project instructions or silently install a missing plugin.

Codex Security distinguishes repository/scoped scans, diff scans, threat modeling, validation, and remediation workflows. Choose the requested scope rather than launching every workflow. [Official Codex Security documentation](https://learn.chatgpt.com/docs/security/plugin).

Claude documents `/security-review` for on-demand change review and a separate codebase security scanner plugin. Verify availability and permitted scope; these are different capabilities. [Claude security reviews](https://support.claude.com/en/articles/11932705-automated-security-reviews-in-claude-code), [Claude Security](https://support.claude.com/en/articles/14661296-use-claude-security).

For changes to authentication, ownership/tenant checks, queries, uploads, outbound requests, webhooks, or tool execution, trace the affected boundary and verify denied as well as allowed behavior. For a substantial new system or changed trust boundary, record the relevant assets, actors, entrypoints, and failure consequences. A full scan remains a separately scoped task when needed.

## Imported instructions

Apply [resource intake](resource-intake.md) to agent/skill/MCP/hook configuration. Inspect permissions, embedded commands, persistence, outbound data, dependencies, and instruction injection. A scanner's own provider/network behavior also needs review.

[SkillSpector](https://github.com/NVIDIA/SkillSpector) is retained solely as a source of inspection ideas. No installation or execution is part of this library workflow. Its documented default LLM mode transmits eligible contents, and static mode can still query OSV with dependency coordinates; do not describe it as automatically offline. No scan has been performed by citing it.
