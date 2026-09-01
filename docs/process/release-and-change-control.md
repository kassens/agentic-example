# Release, Maintenance, and Change Control

## Release prerequisites

A software release candidate must have:

- Authorized change records and approved requirement/design baselines.
- Completed implementation and peer review.
- Passing formal verification for applicable requirements and risk controls.
- Completed traceability with no unexplained orphan links.
- Resolved or formally accepted anomalies and deviations.
- Updated risk, cybersecurity, usability, clinical/performance, privacy, supplier, and regulatory records as applicable.
- Reproducible build, controlled dependencies/configuration, SBOM where applicable, and artifact integrity identifiers.
- Release notes, installation/deployment, migration, rollback, monitoring, service, and recovery instructions.
- Approved labeling/user information where software changes affect it.

## Release gate

The release record identifies the exact source commit, build/artifact digest, configuration, target environment/device, included change records, verification summary, known anomalies, residual-risk decision, approvers, and approval date.

Only designated humans may authorize release or accept residual risk. An agent may assemble the record but must leave approval fields unapproved.

## Change control

Every change to an approved or released baseline—including code, requirements, tests, infrastructure, dependencies, models, prompts, datasets, build tools, configuration, security controls, and suppliers—requires impact analysis proportionate to risk.

Assess impact on:

- Intended purpose, indications, claims, users, environments, and classification.
- Requirements, architecture, interfaces, essential performance, and risk controls.
- Safety, cybersecurity, privacy, usability, clinical/performance evidence, and data integrity.
- Verification, validation, regression, labeling, training, deployment, service, and rollback.
- SOUP/SBOM, suppliers, licenses, vulnerabilities, and support lifecycle.
- Existing devices, stored data, backward compatibility, and field actions.
- Regulatory submissions, certificates, notified-body notification, and technical documentation.

Quality/Regulatory determines whether a change is significant/substantial and whether external review or notification is required. Agents must not make that determination independently.

## Maintenance and post-release inputs

Feed defects, logs, complaints, incidents, vulnerability reports, penetration-test findings, support cases, supplier notices, dependency/model drift, and post-market data into controlled triage.

For each input:

1. Preserve the original report and affected versions.
2. Assess safety, security, regulatory, and field impact promptly.
3. Initiate vigilance, field action, disclosure, CAPA, or escalation under the QMS when required.
4. Create a controlled change for remediation.
5. Update risk analysis and applicable lifecycle records.
6. Re-verify the fix and justified regression scope.
7. Monitor effectiveness after release.

## Definition of done

An engineering task may be called **implemented** after reviewed code and local checks. It may be called **verified**, **validated**, or **released** only when the corresponding controlled gate and human approvals have occurred.

Passing CI, merging a pull request, or deploying an artifact does not by itself constitute regulatory release.
