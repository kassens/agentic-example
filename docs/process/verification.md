# Verification Process

## Principle

Verification demonstrates with objective evidence that specified requirements and risk controls were correctly implemented. It is different from validation, which demonstrates that the product meets user needs and intended use.

Agent-generated code, reviews, test cases, simulations, or summaries become evidence only after controlled execution or review under the approved process.

## Verification planning

Define before formal execution:

- Test-case ID, verification-record ID, and linked requirement/risk-control IDs.
- Method and level: review, analysis, static analysis, unit, integration, system, security, performance, or other test.
- Test configuration, environment, tools, fixtures, datasets, and prerequisites.
- Procedure and expected results.
- Quantitative acceptance criteria, including boundaries and tolerances.
- Required independence and reviewer/approver roles.
- Evidence to retain and anomaly handling.
- Regression scope and rationale.

Acceptance criteria must not be relaxed after results are known without an approved requirement/change update and re-execution.

## Test-design expectations

Cover as applicable:

- Nominal workflows and every normative requirement statement.
- Boundary values and equivalence classes.
- Invalid, missing, malformed, delayed, duplicated, and out-of-order inputs.
- Timeouts, retries, concurrency, interruption, restart, rollback, and recovery.
- Resource exhaustion and external dependency failure.
- Authorization, privilege boundaries, data isolation, injection, tampering, and audit events.
- Risk-control effectiveness and attempts to bypass the control.
- Upgrade, migration, compatibility, installation, and removal.
- Regression of affected and justified neighboring behavior.

Code coverage is supporting information, not proof of requirement coverage.

For product AI/agent behavior, use controlled evaluation datasets, repeated trials where nondeterminism exists, pre-specified statistical thresholds, clinically/risk-relevant subgroups and failure modes, adversarial cases, tool-permission tests, and human-oversight tests. Retain exact model and prompt/configuration versions.

## Execution

1. Confirm protocol approval and independence requirements.
2. Identify the exact build/commit and test-environment configuration.
3. Confirm prerequisites and calibration/qualification status where applicable.
4. Execute the protocol without undocumented deviation.
5. Capture actual results and immutable/raw evidence where practical.
6. Record every deviation and unexpected result, even if the final outcome appears acceptable.
7. Create anomaly records and link them to affected requirements, risks, and runs.
8. Have the authorized reviewer assess results and dispositions.

Agents must report failed commands and incomplete runs. They must not summarize partial execution as a pass.

## Pass/fail and anomalies

A requirement passes only when all approved acceptance criteria are met on the identified configuration and the required evidence is retained. A rerun does not erase a prior failure; link both runs and the anomaly disposition.

Classify and handle anomalies under the QMS. Any accepted unresolved anomaly requires documented rationale, impact/risk assessment, approval by authorized roles, user-facing disclosure where required, and linkage to the release.

## Verification summary

Before Gate G4, report planned versus executed tests; pass/fail/not-run counts; deviations; open anomalies by severity; requirements and risk controls without passing evidence; regression scope; environment/configuration; and reviewer approval status.

Executable test code belongs under `tests/`; controlled protocols and executed records belong under `docs/project/verification/` or the approved external record system. Use `docs/templates/verification-record.md` for each verification record and `docs/templates/traceability-matrix.md` for coverage.
