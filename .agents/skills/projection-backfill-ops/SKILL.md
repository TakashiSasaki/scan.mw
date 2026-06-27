# projection-backfill-ops

## Purpose
This skill consolidates the operations related to Entity/Fact/Projection (EFP) migration, reconciliation, planning, and backfill execution design.

## When to use
Use this skill when performing projection backfills, reconciling EFP models, validating operational metrics, or executing dry-runs for projection rules.

## Inputs and assumptions
- Operations are executed via `npm run ops:*` scripts defined in `package.json`.
- These operations rely on files in the `scripts/` directory.

## Procedure
To perform projection backfill or reconciliation tasks, utilize the available npm scripts. For example:
- **Recompute summaries**: `npm run ops:recompute-projection`
- **Reconcile summaries**: `npm run ops:reconcile-projection`
- **Report reconciliation**: `npm run ops:report-projection-reconciliation`
- **Plan canary writes**: `npm run ops:plan-projection-canary-writes`
- **Validate canary writes**: `npm run ops:validate-projection-canary-writes`
- **Assess backfill readiness**: `npm run ops:assess-projection-backfill-readiness`

## Safety rules
- Do not execute backfill operations in non-interactive or non-dry-run mode without explicit user confirmation.
- Passing readiness validation does not authorize broad rollout or UI read switching.
- These operations should only evaluate or propose changes locally or safely in Firebase. Do not expose live credentials in logs.

## Verification
- Inspect the output of the script to verify evidence passes (`dry-run-evidence-pass`).
- Read generated validation output logs or evidence artifact manifests locally to verify success.

## Related files
- `scripts/*.mjs`
- `package.json`
