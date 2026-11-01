# Resources and adoption decisions

Reviewed 2026-11-01 through source-page inspection. These are untrusted references, not activated instructions. This pass adds original guidance and source credit; it copies no new upstream skill bodies, scripts, installers, or plugins. Upstream commit identities for this pass are unverified. Inspection is not an exhaustive audit, tool test, or SkillSpector scan.

| Resource | Useful topic | Decision and review limit |
| --- | --- | --- |
| [Ponytail](https://github.com/DietrichGebert/ponytail) | Reuse existing code/platform capabilities and keep changes small | Principles considered in build guidance; README, core skill, and license inspected. No runtime adopted. |
| [Superpowers](https://github.com/obra/superpowers) | Clarify design and verify completion claims | Principles considered in workflow guidance; README, verification skill, and license inspected. No mandatory delegation or framework installation. |
| [gstack](https://github.com/garrytan/gstack) | Product, engineering, design, and QA review perspectives | Selected questions considered in workflow/design guidance; README, engineering-plan skill, and license inspected. Helpers, telemetry, state services, and release automation omitted. |
| [Matt Pocock skills](https://github.com/mattpocock/skills) | Composable engineering workflows | Existing adapted editions retained with their own provenance. The current public collection is protected unchanged. No upstream update performed. |
| [ECC](https://github.com/affaan-m/ECC) | Durable context, verification, separation of skills/rules/hooks | Principles considered in workflow guidance; README, strategic-compaction skill, and license inspected. No hooks, memory runtime, or installer adopted. |
| [Floorplan](https://github.com/haydenschmitty/floorplan) | Evidence-linked architecture maps and visible request flows | README and skill page inspected; mapping idea considered in design guidance. Optional deeper procedure review deferred. No renderer, local server, plugin, or helper copied/run. |
| [SkillSpector](https://github.com/NVIDIA/SkillSpector) | Instruction, tool, persistence, exfiltration, and supply-chain review | Reference-only input to resource intake/security guidance. README/categories and license inspected; no scanner installed or run. |
| [Context7](https://github.com/upstash/context7) | Retrieve library documentation | Reference-only optional capability in host setup. README inspected; no MCP server installed, connected, or tested. |

The six learning repositories above (Ponytail, Superpowers, gstack, Matt, ECC, Floorplan) display MIT repository licenses; SkillSpector displays Apache-2.0. This observation does not establish file-specific or bundled third-party rights. Verify the exact selected files and preserve required notices before any future copying. Original synthesis is distinguished from existing licensed adaptations.

## Where the ideas are used

- [Agent workflow](../guides/agent-workflow.md): scope, one primary procedure per stage, reuse, useful review perspectives, evidence, and durable context.
- [Design](../guides/design.md): readable code, thin maintained documentation, and evidence-linked system maps.
- [Resource intake](../guides/resource-intake.md): selection, instruction-surface review, provenance, and attribution.
- [Host setup](../guides/host-setup.md) and [security tools](../guides/security-tools.md): maintained native capabilities and version-sensitive facts, checked against the linked official documentation.

## Maintaining this list

Add a source with its review date/scope, useful question, decision, affected local paths, unknowns, and required notices when material is copied. Refer to per-file provenance for actual adaptations; do not relabel an old edition as current upstream. Keep pending private observations out of this shared catalog. Review version-dependent entries about monthly or after a relevant advisory; no automated downloads or runtime updates are implied.
