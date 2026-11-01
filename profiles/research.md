# Research and statistics profile

Use for empirical studies, modeling, scientific software, and reproducible analysis. Define the question, target population/system, sampling unit, outcome, estimand where applicable, comparator, and hypotheses. Distinguish exploratory from confirmatory work.

Before analysis, record provenance, permitted use, inclusion/exclusion rules, missingness, duplicates, measurement quality, and processing steps. Preserve raw data and identify derived artifacts. Use versioned code, environments, parameters, data checksums/identifiers, and seeds. Document numerical nondeterminism and hardware-dependent results when relevant.

Choose the study design and method based on the question. Identify confounders, selection effects, dependence, batch effects, censoring, and leakage. Explain sample-size/power reasoning when meaningful. State modeling assumptions, primary outcomes, multiplicity handling, uncertainty intervals, and robustness/sensitivity checks before interpreting results. Causal claims need an identification argument beyond association or predictive performance.

Separate train/validation/test, discovery/confirmation, or development/replication data as appropriate. Split dependent observations by participant, group, site, or time when random row splits would contaminate evaluation. Prevent preprocessing or feature selection from learning from held-out data.

Keep a protocol, experiment record, data card, and reproducible entry command. Move reusable logic from notebooks into tested modules; notebooks can remain the inspectable narrative. Test calculations on known examples, invariants, units, boundary cases, and reference outputs with justified tolerances.

Evaluate evidence quality and competing explanations. Record negative and inconclusive findings. Report effect sizes and uncertainty in the context of the design; do not treat a threshold alone as practical or scientific importance. Domain/methods review is needed for claims whose consequences exceed the team’s expertise.

Share a permitted evidence bundle: protocol, data access instructions, code/environment versions, run command, tables/figures, limitations, and claim-to-evidence mapping. Restricted inputs can remain in an approved environment while synthetic fixtures verify the public workflow.
