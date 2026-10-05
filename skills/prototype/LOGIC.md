# Logic prototype

For a question about state transitions or data shape, build a self-contained local HTML/CSS/JS demo when visual interaction will clarify it. Inline the required code; no remote scripts, CDN assets, bundler, or server is needed.

Show the question above the controls. Isolate the model as a reducer, explicit state machine, or small module; the page calls its public interface rather than changing its internals. Render the relevant state after each action using domain labels.

Provide free-play actions and a few resettable scenarios that probe the disputed behavior: ordinary use, an awkward sequence, and an illegal transition if applicable. A deterministic initial state makes observations comparable. Add a targeted assertion or independent expected result when the verdict depends on exact behavior.

Capture the answer and its supporting scenario. Keep the demo local as described in `SKILL.md`; implementation must verify any logic reused from it through the maintained project's checks.
