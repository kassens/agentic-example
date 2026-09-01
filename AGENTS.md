# Agent Instructions

This repository uses a controlled, phase-gated software lifecycle suitable as a baseline for medical-device development. The process is intentionally stricter than ordinary software development.

These instructions apply to every human-assisted or autonomous coding agent operating in this repository.

## Authority and precedence

Follow, in order:

1. Applicable law and regulation.
2. The company's approved quality management system (QMS), SOPs, product plans, and regulatory decisions.
3. Approved project requirements, risk controls, and design baselines.
4. This file and the detailed instructions under `docs/`.

If sources conflict, are missing, or are ambiguous, stop and request direction. Do not invent a compliant interpretation.

## Non-negotiable controls

- Do not implement product behavior without an approved, uniquely identified requirement.
- Do not silently reinterpret or improve an approved requirement. Raise a change record.
- Do not begin implementation until the applicable requirements, design, risk controls, and verification approach have passed their gates.
- Maintain bidirectional traceability from requirement and risk control through design, implementation, verification evidence, and release.
- Treat risk management, cybersecurity, usability, clinical/performance claims, and privacy as lifecycle activities, not final checks.
- Never fabricate test results, reviews, approvals, logs, trace links, or regulatory evidence.
- Never mark your own work approved. Agents may prepare artifacts and evidence; authorized humans approve baselines, residual risk, deviations, and releases.
- Do not weaken a test, acceptance criterion, safety control, security control, or audit trail merely to make a change pass.
- Do not use production patient data, personal data, secrets, or credentials unless an approved procedure and explicit authorization allow it.
- Do not place generated text copied from licensed standards into the repository. Use controlled company copies and cite the applicable clause/version.
- If a requested action could affect patient safety, intended purpose, claims, classification, essential performance, clinical evidence, or released-device behavior, stop until Regulatory/Quality has assessed it.

## Required workflow

For every product change:

1. **Intake and impact analysis** — create or reference a change record; identify affected requirements, risks, software items, interfaces, data, security, usability, and regulatory artifacts.
2. **Requirements** — draft atomic, testable requirements with stable IDs and objective acceptance criteria; obtain human approval and establish a baseline.
3. **Design and risk** — update architecture, detailed design, interfaces, risk analysis, and planned risk controls; review and approve before coding.
4. **Implementation** — change only approved scope on a reviewable branch; preserve configuration, provenance, and review records.
5. **Verification** — execute the pre-specified verification method against the approved requirement and record reproducible objective evidence.
6. **Release** — resolve or formally disposition anomalies; complete traceability and impact assessment; obtain independent Quality/Regulatory release approval where applicable.
7. **Maintenance** — process defects, vulnerabilities, complaints, and other feedback through the same controlled change and re-verification flow.

Exploratory work is permitted only when explicitly labeled **non-product / not for release**, isolated from the controlled product baseline, and prevented from being merged until converted into approved requirements and design.

## Before modifying files

- Read `docs/process/project-flow.md`, `docs/repository-layout.md`, and the relevant process documents.
- Identify the change record and requirement/risk-control IDs. If none exist, stop after drafting the proposed records.
- State the lifecycle phase, gate status, approved scope, verification plan, and files expected to change.
- Inspect the current baseline and preserve unrelated work.

## Repository placement

- Production source belongs under `src/`; do not mix product code with scripts or tests.
- Executable tests belong under `tests/` by level. Formal protocols, executed results, approvals, and traceability belong under `docs/project/` or an approved external controlled system.
- Reusable lifecycle instructions belong under `docs/process/`; reusable record formats belong under `docs/templates/`.
- Product-specific requirements, design, risk, verification, validation, release, change, and anomaly records belong under `docs/project/` as defined in `docs/repository-layout.md`.
- Build output and transient agent artifacts are not controlled source or verification evidence and must not be committed.

## Evidence and reporting

Every completed change report must include:

- Change-record ID and requirement/risk-control IDs.
- Files and configuration items changed.
- Tests and reviews performed, with exact commands and results.
- Environment, tool/model versions, commit SHA, and relevant timestamps when available.
- Deviations, unresolved anomalies, assumptions, and limitations.
- Traceability updates and required human approvals still outstanding.

An agent statement such as "looks correct" or "tests should pass" is not verification evidence.

## Definition of done

A change is not complete or releasable until all applicable items in `docs/process/release-and-change-control.md` are satisfied. Passing tests alone is insufficient.

## Documentation index

- `docs/README.md` — complete process index.
- `docs/repository-layout.md` — required locations for source, tests, and controlled records.
- `docs/process/project-flow.md` — lifecycle phases and approval gates.
- `docs/process/development-guidelines.md` — day-to-day agent and engineering rules.
- `docs/process/requirements-and-traceability.md`
- `docs/process/design-and-risk.md`
- `docs/process/implementation.md`
- `docs/process/verification.md`
- `docs/process/release-and-change-control.md`
- `docs/templates/` — required record formats.
- `docs/reference/regulatory-context.md` — regulatory context and official references.
