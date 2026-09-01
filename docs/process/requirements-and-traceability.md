# Requirements and Traceability

## Purpose

Requirements are the controlled agreement about what the product must do and the basis for design, risk control, verification, validation, and release. Agents must not infer missing product requirements from implementation details.

## Requirement classes and IDs

Use stable IDs in the form `<PROJECT>-<TYPE>-<NUMBER>`, for example `AEX-SWR-0027`. Define the short project prefix in the approved project plan. Do not encode document revision, status, component, or release version in the ID.

| Type | Record type | Example |
|---|---|---|
| `UN` | User need | `AEX-UN-0001` |
| `SYS` | System requirement | `AEX-SYS-0014` |
| `SWR` | Software requirement | `AEX-SWR-0027` |
| `IF` | Interface/data requirement | `AEX-IF-0006` |
| `SEC` | Cybersecurity/privacy requirement | `AEX-SEC-0012` |
| `HAZ` | Hazard or threat record | `AEX-HAZ-0003` |
| `RC` | Risk-control requirement | `AEX-RC-0009` |
| `DES` | Controlled design element/decision | `AEX-DES-0008` |
| `TC` | Verification test case/specification | `AEX-TC-0041` |
| `VER` | Executed verification record | `AEX-VER-0027` |
| `VAL` | Validation record | `AEX-VAL-0004` |
| `CR` | Change record | `AEX-CR-0004` |
| `ANOM` | Anomaly | `AEX-ANOM-0011` |

Identifiers are never reused. Superseded requirements retain history and links to their replacements. Test-case IDs and executed verification IDs are deliberately distinct: a controlled `TC` may be executed many times, producing multiple `VER` records.

## Required attributes

Each requirement contains the fields in `docs/templates/requirement.md`, including:

- ID, title, normative statement, rationale, source, owner, status, and baseline.
- Safety/security relevance and linked hazards or risk controls.
- Objective acceptance criteria and planned verification method/level.
- Parent and derived-requirement links.
- Design, implementation, verification, anomaly, and change links.

## Writing rules

- Use one mandatory behavior per requirement, normally expressed with **shall**.
- Define actor/component, condition, behavior, measurable limit, and response to failure where applicable.
- Avoid subjective terms such as fast, user-friendly, robust, appropriate, normal, and secure unless quantitatively defined.
- Define units, tolerances, boundary conditions, timing, data validity, error behavior, and operating environment.
- State what is out of scope when confusion is foreseeable.
- Do not embed design choices in a requirement unless the design constraint is intentional and justified.
- Every requirement must be feasible and verifiable without relying solely on author judgment.

## Review and baseline

A requirements review checks completeness, correctness, consistency, clarity, feasibility, verifiability, risk coverage, regulatory impact, and traceability. Required domain, Quality, Regulatory, safety, security, privacy, clinical, and usability reviewers depend on impact.

Allowed states are `Draft`, `In review`, `Approved`, and `Superseded`. Only `Approved` requirements belong to a controlled baseline and authorize implementation.

## Traceability

Maintain bidirectional links:

`source/user need -> system/software requirement -> design element -> implementation/configuration item -> test case -> executed verification record -> result/anomaly -> release`

Hazards and risk controls join this chain at every affected level. A traceability check must detect:

- Requirements without an approved source or rationale.
- Requirements without design allocation or verification.
- Code or configuration changes without requirements.
- Risk controls without implementation and effectiveness verification.
- Tests that do not verify an approved requirement.
- Released items with unresolved or unapproved anomalies.

Use `docs/templates/traceability-matrix.md` until a validated requirements-management system provides equivalent controlled records.

Automated test code should include or declare its `TC` ID and linked requirement/risk-control IDs in a searchable, machine-readable form supported by the chosen test framework. Filenames and test names may contain IDs for discoverability, but the controlled traceability record remains authoritative. Many-to-many mappings are expected; do not force one test per requirement.

## Requirement changes

After baseline approval, changes require a project-prefixed `CR` record, impact analysis, approval, baseline revision, and updates to design, risk, verification, validation, and regulatory artifacts as applicable. Never overwrite history or alter acceptance criteria after seeing test results without recording the change and invalidating/repeating affected verification.
