# Adopt a selected project kit

The destination project owns its instructions, real commands, data rules, architecture, and decisions. Use portable selected snapshots that include their required guidance, companions, and notices.

## Start with the core

1. Inspect the destination's existing instructions and changes. Merge useful parts of [AGENTS](../templates/AGENTS.md), [CLAUDE](../templates/CLAUDE.md), and [SECURITY](../templates/SECURITY.md) templates; do not overwrite existing project decisions or copy this library's root maintenance instructions.
2. Select the relevant [workflow](agent-workflow.md), [design](design.md), [verification](verification.md), and [security](../SECURITY.md) guidance. Copy it under a project-owned guidance folder, keeping linked companions or adjusting links deliberately. Add pointers only to files actually adopted.
3. Add original `foundry-plan`, `foundry-build`, `foundry-review`, or `foundry-handoff` workflows when useful. They are self-contained folders under `workflows/`; select only the current jobs. The existing Matt collection in `skills/` offers other procedures. Choose one primary workflow per stage.
4. Record the public repository URL/commit, selected paths/hashes, destinations, local adaptations, dependencies/notices, and update policy in [the adoption manifest](../templates/adoption-manifest.md). Fill actual commands and remove template markers before use.

## Optional selections

| Work | Suggested additions |
| --- | --- |
| Small application | `profiles/app.md`, `foundry-intake` or `foundry-ideate`, and `foundry-design` as needed |
| Operated service | `profiles/production.md`, release plan and `foundry-release` |
| Research or biology | Relevant research/biology profiles, research protocol/experiment records, and `foundry-research` |
| ML or LLM systems | Relevant profiles, evaluation/model/data templates, `foundry-ml` or `foundry-llm` |
| Agent runtime design | `guides/agent-systems.md`, agent-system template, and `foundry-harness` |

These are selections, not automatically installed bundles. Keep core instructions brief and defer unused documents. No stack, cloud service, external package, or scanner is required by the kit itself.

## Skill copies and host checks

Copy each selected whole workflow folder into `.agents/skills/<name>/` for Codex or `.claude/skills/<name>/` for Claude Code. Keep duplicated host copies consistent. Other hosts may read exact skill paths explicitly. [Host setup](host-setup.md) links current official discovery guidance. Confirm visibility in the actual host and try an appropriate bounded task; visibility alone does not establish reliability.

For Matt workflows, preserve whole selected folders and their referenced skill/Markdown companions. Inspect the actual references rather than assuming a folder is self-contained. Retain `skills/LICENSE`, applicable [attribution](../ATTRIBUTION.md), and additional credits such as `skills/pr/CREDITS.md` when adopting the corresponding material. This public edition remains unchanged; do not substitute another edition during adoption.

## Updates and contributions

Existing projects refresh selected guidance deliberately against their adoption record, preserving local rules. Record accepted changes, duplicates skipped, conflicts, and unrun checks. A change to this library does not automatically change application repos.

General improvements may be edited and published from an authorized checkout. Share only material you are permitted to make public, preserve source/attribution records, and keep the existing Matt files unchanged. Preparing local changes does not itself commit or push them.
