# Production, DevOps, and CI/CD profile

Use when people rely on an operated service, application, scheduled data pipeline, or deployed model. Identify the owner, environments, critical journeys, failure consequences, acceptable downtime/data loss, and operating budget.

## Delivery

Use version control, reviewable changes, required branch checks, locked dependency installs, and repeatable builds. Ordinary CI should run relevant formatting/lint/types/tests, secret/dependency checks as available, and build verification. Separate expensive model/research jobs with their own budgets.

Produce an identifiable artifact and promote the same artifact between environments when practical. Keep environment configuration and secrets separate. Use infrastructure as code where useful; review privileges and diffs. Choose continuous deployment only when risk, tests, and recovery make it appropriate. Do not deploy automatically merely because CI passed.

Protect CI credentials from untrusted code, use least privilege, immutable reviewed action versions, and short-lived workload identity when available. Preserve existing authority for releases; require missing environment authority at the actual boundary.

## Operate and recover

Define service indicators and objectives from user needs. Add structured redacted logs, metrics, traces where useful, and actionable alerts with an owner. Monitor correctness/freshness for pipelines and quality/drift for ML/LLM services alongside uptime, latency, errors, and cost.

Use a release plan covering smoke checks, rollout/canary if justified, migrations/backfills, compatibility, rollback limits, forward recovery, and abort conditions. Practice backup restoration and incident response. A documented backup that has never been restored is weak evidence of recoverability.

Bound expensive/public operations with quotas and abuse controls. Plan capacity from measured workloads. Keep runbooks for real failure modes, access revocation, provider outage, corrupted state, and billing anomalies. Review incident causes and improve the system rather than adding blame or broad instructions for every failure.

Track delivery lead time, deployment frequency, failed changes, and recovery in context. Use these as improvement signals rather than targets that invite gaming. Include user outcomes, reliability, correctness, and cost. Retire unused services and credentials deliberately.
