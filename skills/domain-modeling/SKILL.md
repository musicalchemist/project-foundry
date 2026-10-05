---
name: domain-modeling
description: "Build or sharpen project terminology, resolve ambiguous domain relationships, and maintain a glossary and consequential architecture decisions."
---

# Domain modeling

Use the existing glossary and decision layout. A root `GLOSSARY.md` serves a single context; an existing `GLOSSARY-MAP.md` points to separate contexts. Create documents only when a resolved term or consequential decision needs recording.

Challenge terms that conflict with the glossary or mean several things. Propose precise names, then test relationships with concrete edge cases. Check existing code against claims about current behavior; distinguish implemented behavior from the proposed model.

When a term is resolved, update the relevant glossary using [GLOSSARY-FORMAT.md](GLOSSARY-FORMAT.md). Keep implementation choices in design documents. For scientific concepts, distinguish project conventions from accepted definitions and unresolved hypotheses; do not settle an empirical question by naming it.

Record a decision when reversal is costly, the reason would surprise a future reader, and real alternatives were considered. Use [ADR-FORMAT.md](ADR-FORMAT.md), keeping unresolved choices proposed rather than accepted. Reuse existing decisions; identify evidence that warrants reopening one.

Return resolved terms, changed document paths, and remaining ambiguities that affect the next task. Reading a glossary alone does not require this workflow.
