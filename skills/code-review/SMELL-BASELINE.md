# Design heuristics for the Standards axis

Use Fowler's code-smell vocabulary to identify a possible design problem in the changed code. Name the evidence and likely maintenance cost before proposing a correction; a documented repo choice can justify the shape.

| Possible smell | Evidence to investigate |
| --- | --- |
| Mysterious Name | A name conceals the value's or operation's role |
| Duplicated Code | Repeated logic implements the same changing rule |
| Feature Envy | Behavior repeatedly navigates another module's data |
| Data Clumps | The same related values travel through several interfaces |
| Primitive Obsession | A domain concept loses validation or meaning in a primitive |
| Repeated Switches | Multiple dispatch trees repeat the same domain alternatives |
| Shotgun Surgery | One rule change requires scattered edits |
| Divergent Change | Unrelated reasons cause changes to one module |
| Speculative Generality | New extensibility has no supported requirement |
| Message Chains | Callers depend on a long internal navigation path |
| Middle Man | Delegation adds a boundary without a useful contract |
| Refused Bequest | An implementation rejects much of its inherited contract |

Label these as possible smells. Propose a small correction only when the evidence supports a useful boundary, term, or responsibility change; the list does not require twelve findings or twelve refactorings.
