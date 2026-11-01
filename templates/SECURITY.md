# Project security policy

Template: replace `{fill ...}` fields and remove this sentence before adoption. Incorporate the selected portable baseline from Project Foundry; this project policy owns actual contacts and boundaries.

## Reporting and ownership

- Security owner: {fill accountable person/team}
- Private reporting channel: {fill approved channel; do not invent an address}
- Supported versions/environments: {fill scope}
- Incident escalation: {fill contact/process}

## Assets and trust boundaries

{fill sensitive data/secrets, user/tenant roles, privileged services, agent/tool access, and high-impact failure scenarios}

## Required controls

Keep secrets out of source, prompts, notebooks, client bundles, logs, and artifacts. Enforce authentication/authorization on the server, including object and tenant boundaries. Validate inputs, use safe queries/encoding, restrict uploads, verify webhooks, and bound abuse/expensive operations. Clear app-owned auth state and invalidate relevant server sessions at logout.

Use reviewed dependencies, locked builds, least-privilege CI/cloud access, and isolation for untrusted code. Treat retrieved and generated text as data. Enforce tool permissions outside prompts.

## Data and agent use

{fill permitted datasets, consent/licenses/approvals, providers and destinations, retention/deletion, trace redaction, and employer requirements}

## Authorization and release

{fill routine permissions already granted, dependency-install policy, production/migration/destructive/credential boundaries, and release owner}

## Verification and recovery

{fill concrete security checks, cross-user/tenant tests, scans, backup/restore evidence, incident and rollback/forward-recovery procedures}
