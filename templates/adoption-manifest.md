# Project Foundry adoption manifest

- Project/repo path, work mode, agents and environments:
- Source folder, version/date, adopted date and owner:
- Rigor tier and selected profiles with reasons:
- Adoption mode: copy snapshot / explicit local reference / host-specific import.
- For a public Foundry snapshot: public repository URL and commit, selected relative paths and local hashes; include required guidance and companions so the snapshot is portable.

| Source path relative to Project Foundry | Destination or resolved reference | Mode | Required edits/dependencies | Reason |
| --- | --- | --- | --- | --- |
| templates/AGENTS.md | AGENTS.md | adapt/merge | Real commands, boundaries, existing pointers | Project instructions |
| templates/CLAUDE.md | CLAUDE.md | adapt/merge | AGENTS.md must exist | Claude adapter, if used |
| templates/SECURITY.md | SECURITY.md | adapt/merge | Project owner, controls, authority and data rules | Project policy |

## Skills

Record each selected source folder, host destination(s), name, dependencies/setup, and current/deferred status. Ensure duplicated host copies match. For third-party copies, retain license, known source revision/hashes, current local hashes, review notes, and substantive adaptations. Mark unverified upstream fields unknown for conversation-derived adaptations; do not substitute a local hash for upstream identity. Catalog selection alone does not activate a skill or authorize its tool effects.

## Completion and updates

- All referenced files exist and are accessible in the destination:
- Template fields resolved and commands checked:
- Host instruction/skill discovery checked:
- Relevant writing/security context copied or explicitly accessible:
- Existing local decisions preserved:
- Deferred guidance and activation conditions:
- Update policy: compare/review changes; no silent replacement.
- Last guidance refresh, changes accepted/skipped, and next review trigger:
