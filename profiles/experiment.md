# Experiment profile

Use for a disposable prototype, technical spike, or feasibility investigation. Set the question before writing code. Choose synthetic/public data where appropriate and keep actual security/data constraints in force.

Record the hypothesis or uncertainty, simplest comparator, time/compute cap, success/failure criteria, and the decision the result will inform. Build only enough to answer it. A throwaway UI can test a user flow; it does not establish backend security or scalability.

Verify the critical path with representative inputs and known edge cases. Preserve the input versions, command/environment, result, and limits. A brief plus experiment record is often enough. Avoid production infrastructure and large test suites for disposable code unless the experiment itself requires them.

At the end choose: discard, repeat with a changed hypothesis, or promote. Promotion requires identifying what must be rebuilt or hardened, including access controls, reproducibility, tests, data handling, and ownership. Do not silently turn an experiment into a service for real users.
