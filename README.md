# Project Foundry

A portable engineering core and optional workflows for building with coding agents. Select the guidance a project needs, copy it into that project, and adapt it to the actual code, commands, risks, and decisions. Keep required guidance and companions together so the checkout is self-contained.

Start with [adoption](guides/adoption.md). For a small project, use the instruction templates and the relevant parts of [agent workflow](guides/agent-workflow.md), [design](guides/design.md), [verification](guides/verification.md), and [security](SECURITY.md). Load procedures when needed rather than importing every document into agent context.

| Need | Read |
| --- | --- |
| Choose a core or optional pack | [Adoption guide](guides/adoption.md) |
| Start a new project | [Kickoff prompt](templates/new-project-kickoff.md) |
| Refresh an existing repo or contribute a lesson | [Guidance sync prompt](templates/sync-guidance.md) |
| Codex/Claude setup facts | [Host setup](guides/host-setup.md) |
| Evaluate a new resource | [Resource intake](guides/resource-intake.md), [resource catalog](references/resources.md) |
| Select security checks | [Security tools](guides/security-tools.md) |
| Original planning/build/review procedures | [Foundry workflows](workflows/) |
| Existing Matt Pocock adaptations | [Skills](skills/), [attribution](ATTRIBUTION.md) |

The existing Matt collection in `skills/`, including companions, credits, and license, is preserved unchanged. Original Foundry workflows live separately in `workflows/`. Choose one primary procedure per stage; the two collections are not meant to be loaded wholesale together.

[best-practices.md](best-practices.md) remains the practical external-content/tool baseline. [about.md](about.md) retains the original longer explanation of the Matt-based workflow. Root [AGENTS.md](AGENTS.md) governs library maintenance; use [templates/AGENTS.md](templates/AGENTS.md) for application repos.

No external plugin, scanner, MCP server, or helper is installed by reading or copying this resource. Source-page inspection and structural verification are distinguished from security scans and behavioral testing.
