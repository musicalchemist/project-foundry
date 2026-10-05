---
name: code-review
description: "Review a specified change set along separate standards and specification axes, citing evidence for violations, missing requirements, and unrequested behavior."
---

# Review standards and specification separately

Establish the requested change set: a PR, branch comparison, commit range, staged/unstaged changes, or named files. Resolve a supplied base to a commit and record comparison semantics; a merge-base comparison and direct snapshot comparison answer different questions. Include uncommitted work when requested. Report an empty scope or invalid reference before reviewing.

Find the accepted specification in supplied context or local project documents. Use an external issue only when access is authorized; no tracker setup is required. If the spec is unavailable, mark the Spec axis unevaluated.

Review the same change set in two passes:

- **Standards:** cite applicable repo rules and their source. Use [SMELL-BASELINE.md](SMELL-BASELINE.md) for design heuristics; repo decisions override that baseline. Treat possible smells as judgment calls, and avoid repeating findings already covered by a verified tool result.
- **Spec:** map requirements to the changed behavior and acceptance evidence. Identify missing/partial requirements, incorrect implementations, and behavior outside agreed scope.

For each supported finding, provide the path/line, trigger, consequence, relevant rule or requirement, and minimum correction. Separate demonstrated defects from hypotheses needing a check.

Return Standards and Spec findings separately, with counts, material issues per axis, and coverage limits. Findings on one axis do not compensate for the other. This workflow reviews and reports; fixing findings or dispatching parallel agents is a separate task choice.
