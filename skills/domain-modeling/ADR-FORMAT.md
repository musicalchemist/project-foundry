# Decision record format

Use the project's existing decision directory and numbering. Otherwise create `docs/adr/0001-slug.md` when the first record is needed, incrementing the highest existing number.

```md
# Decision title

Status: proposed | accepted | superseded by ADR-NNNN

Context, alternatives considered, decision, and the reason for choosing it.
```

A paragraph can suffice. Add consequences, evidence, and revisit conditions when future work depends on them. Keep proposed and accepted decisions distinct. Supersede an old decision with a linked record rather than silently rewriting its history.

Record decisions whose reversal is costly, rationale would surprise a future reader, and alternatives involved a real tradeoff. Examples include data ownership, integration contracts, provider lock-in, and constraints absent from the code. Omit routine choices with no useful rationale to preserve.
