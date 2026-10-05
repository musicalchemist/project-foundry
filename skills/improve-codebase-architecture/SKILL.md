---
name: improve-codebase-architecture
description: "Survey a scoped existing codebase for architectural friction and rank behavior-preserving refactoring candidates before implementation."
disable-model-invocation: true
---

# Survey refactoring opportunities

Use [codebase-design](../codebase-design/SKILL.md) for deep-module and interface criteria. Read relevant glossary terms and decisions. Scope the survey to the user's subsystem or pain point; otherwise inspect available change history to identify recurring hotspots. State the evidence used when history is unavailable.

Trace a concrete change or failure through the area. Look for scattered ownership of one concept, interfaces nearly as complex as their implementation, leaking internals, and tests that miss integration behavior. Apply the deletion test: would removing a suspected shallow module concentrate complexity or merely move it?

Report candidates in local Markdown, with Mermaid source only when a diagram clarifies the relationships. For each candidate give files, observed friction, proposed consolidation, preserved contracts, before/after structure, verification needs, and confidence. Tie confidence to evidence; a stylistic preference alone is speculative. Mark conflicts with existing decisions and the evidence that could justify reopening them.

Recommend the candidate with the strongest benefit under current constraints. Stop after the survey unless the task already authorizes exploring a named candidate. Use [grilling](../grilling/SKILL.md) for unresolved design choices, then [domain-modeling](../domain-modeling/SKILL.md) when terms or consequential decisions change. Reuse approved choices without repeating the interview.

Return the report path and the first characterization or design step. Surveying does not authorize behavior changes, mass rewrites, external reports, or launching subagents. No CDN report scaffold or parallel-design companion is needed.
