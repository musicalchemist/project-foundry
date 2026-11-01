# Computational biology and bioinformatics profile

Use alongside the research profile for biological data analysis, modeling, biotechnology research software, and bioinformatics pipelines. Computational evidence needs both software verification and biological interpretation.

Record organism, sample/participant identity rules, assay, biological and technical replicates, experimental conditions, reference assembly, annotation release, accession identifiers, and processing versions. Preserve identifiers and transformation history. Record coordinate conventions, strand, units, normalization, and missingness; silently mixing assemblies or annotations can invalidate results.

Inspect sample metadata, contamination/quality signals, batch effects, confounders, selection, and dependence. Choose domain-specific QC thresholds with reasons and record excluded samples. Avoid treating technical replicates as independent biological observations. Keep outcome/label and related-subject leakage out of validation.

Specify pipeline inputs/outputs and run commands; choose a workflow engine when dependency tracking, parallelism, restartability, or provenance justifies it. Pin tools/reference data and record hashes or accessions. Budget memory, storage, runtime, and compute before large runs. Use small synthetic/public fixtures for smoke tests and known/reference cases for validation.

For human genomic/clinical data, establish permissions, consent/approval requirements, approved compute/storage/provider destinations, access controls, retention, and sharing limits. Deidentification does not establish permission or eliminate reidentification risk. Work with synthetic/public data while restricted access is unresolved. Agents must not upload such data to outside services without authorization.

Distinguish computational predictions, statistical associations, causal interpretations, and experimentally validated mechanisms. Record annotation bias, cohort limitations, multiplicity, and validation gaps. Obtain domain review before making consequential biological claims. Clinical translation or wet-lab follow-up requires its own qualified review and approvals; a passing software pipeline does not provide them.
