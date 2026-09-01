# Project Flow: Controlled V-Model

This baseline implements a strict waterfall lifecycle using V-model traceability. Activities may inform one another, but approved baselines are changed only through formal change control.

Agents may draft documents, code, tests, and evidence. Agents are not approval authorities.

## Phase 0 — Change intake and planning

### Activities

- Define the problem, intended outcome, product context, and proposed scope.
- Determine whether the change affects intended purpose, claims, device classification, essential performance, patient/user safety, clinical evidence, usability, cybersecurity, privacy, interoperability, or production.
- Identify applicable QMS procedures, standards, regulatory artifacts, suppliers, and released configurations.
- Create a change record and lifecycle plan.

### Outputs

- Project-prefixed change record (`<PROJECT>-CR-####`).
- Initial impact analysis.
- Development and verification plan appropriate to risk.

### Gate G0 — Change authorized

An authorized human approves scope, responsibilities, required artifacts, and whether Regulatory/Quality participation is required.

## Phase 1 — Requirements

### Activities

- Create or update user, system, software, interface, data, risk-control, security, and regulatory requirements.
- Make every requirement atomic, unambiguous, feasible, uniquely identified, and objectively verifiable.
- Define acceptance criteria and planned verification methods before implementation.
- Resolve contradictions and bidirectionally link derived requirements to their source.

### Outputs

- Approved requirement records.
- Initial traceability matrix.
- Updated risk analysis and verification strategy.

### Gate G1 — Requirements baseline

Engineering, product/domain, Quality, and Regulatory roles approve as applicable. Open placeholders, ambiguous acceptance criteria, and orphan requirements block the gate.

## Phase 2 — Design and risk controls

### Activities

- Define architecture, components, interfaces, data flows, state transitions, failure behavior, and external dependencies.
- Allocate requirements and risk controls to design elements.
- Perform or update safety, security, usability, privacy, and supplier risk analyses.
- Specify verification methods, test environments, datasets, tools, and independence.

### Outputs

- Architecture and detailed design records.
- Interface and data specifications.
- Updated risk-control implementation and verification links.
- Approved verification protocols or specifications.

### Gate G2 — Design baseline

Reviewers confirm the design implements the requirements, risks are controlled as far as required, interfaces are defined, and verification is feasible. Coding begins only after approval.

## Phase 3 — Implementation

### Activities

- Implement only approved scope under configuration control.
- Perform code review, static analysis, unit testing, dependency review, and secure-development checks as applicable.
- Record provenance for agent-generated changes and third-party components.
- Report discovered requirement/design defects instead of silently compensating in code.

### Outputs

- Version-controlled implementation.
- Review and unit-test evidence.
- Updated software bill of materials and configuration records where applicable.
- Anomaly and change records.

### Gate G3 — Implementation complete

All planned implementation is reviewed and configuration-controlled; blocking anomalies are resolved; the build is reproducible and ready for formal verification.

## Phase 4 — Verification

### Activities

- Execute approved protocols against the controlled build and test environment.
- Verify every applicable requirement and risk control.
- Record actual results, logs, environment, configuration, deviations, and anomalies.
- Perform regression testing based on documented impact analysis.

### Outputs

- Completed verification records and objective evidence.
- Verification summary report.
- Completed traceability matrix.
- Anomaly dispositions and regression evidence.

### Gate G4 — Verification accepted

An authorized reviewer independent of implementation where practicable confirms protocol adherence, evidence integrity, traceability completeness, and acceptable anomaly disposition.

## Phase 5 — Validation and release

Verification asks whether outputs meet specified requirements. Validation asks whether the resulting system meets user needs and intended use. Product validation, clinical/performance evaluation, and usability validation are governed by applicable QMS and regulatory plans.

### Outputs

- Applicable validation evidence.
- Release notes, known-anomaly list, deployment/rollback instructions, and approved configuration.
- Updated risk, cybersecurity, usability, clinical/performance, and technical documentation as applicable.
- Release checklist and approvals.

### Gate G5 — Release authorized

Only designated human roles may accept residual risk, approve deviations, and authorize release. The released version must be uniquely identifiable and reproducible.

## Phase 6 — Maintenance and post-release monitoring

- Process defects, vulnerabilities, complaints, incidents, supplier changes, model/dependency drift, and field observations through controlled intake.
- Reassess risk and regulatory impact before changing a released baseline.
- Update requirements, design, tests, technical documentation, and post-market records as applicable.
- Re-verify the affected scope plus justified regression scope before release.

## Gate record minimum content

Every gate decision records the baseline/version reviewed, required inputs, reviewers and roles, decision and date, unresolved actions, deviation approvals, and links to objective evidence.
