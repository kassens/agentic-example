# Controlled Implementation

## Preconditions

Implementation may begin only when:

- A change record is authorized.
- Applicable requirements are approved and baselined.
- Design and risk-control implementation are approved.
- Verification methods and acceptance criteria are defined.
- Required tools, environments, dependencies, and suppliers are approved or qualified under the QMS.

If these conditions are absent, an agent may draft the missing artifacts but must not present product code as release-ready.

## Implementation procedure

1. Record the project-prefixed change ID, requirement IDs, risk-control IDs, and approved baseline.
2. Inspect the current branch, configuration, tests, known anomalies, and affected interfaces.
3. Write a bounded implementation plan identifying files, migration/compatibility effects, and planned checks.
4. Implement the smallest change that satisfies the approved design.
5. Add or update unit/component tests and static-analysis configuration without altering approved acceptance criteria.
6. Run local checks and preserve commands/results.
7. Update design, configuration, SBOM/dependency, operational, and traceability records as applicable.
8. Perform peer review and resolve findings under reviewer control.
9. Produce an implementation summary and hand off the controlled build for formal verification.

## Prohibited shortcuts

- Coding from an ambiguous chat prompt without controlled requirements.
- Editing tests to match an implementation when the approved requirement says otherwise.
- Disabling warnings, checks, audit logs, signatures, access controls, or error handling without approved rationale.
- Adding unreviewed dependencies, external services, models, generated artifacts, or telemetry.
- Mixing refactors or dependency upgrades with safety-relevant behavior changes without separate impact analysis.
- Using mock results as evidence that the integrated product passes.
- Committing secrets, personal data, patient data, or proprietary external content.

## Configuration and provenance

Record or pin, as applicable:

- Source commit and branch.
- Compiler/runtime, build tool, operating system/container, and configuration.
- Direct and transitive dependencies and checksums/lockfiles.
- Code generators, agents, models, prompts/configuration, and significant tool versions.
- Feature flags, environment variables by name (never secret value), external-service/API versions, and database/schema migrations.
- Generated-code source and regeneration procedure.

Follow `docs/repository-layout.md` for placement. Test helpers must not be imported by production code, and production behavior must not depend on files under `docs/`.

The formal verification build must be reproducible from controlled source and configuration.

## Implementation review checklist

- Scope matches approved requirements and design.
- Risk controls are implemented without bypass paths.
- Failure and boundary behavior are explicit.
- Security/privacy controls and logging are appropriate.
- Interfaces and backward compatibility are correct.
- Tests cover intended, boundary, error, and negative behavior.
- No unrelated or unexplained changes exist.
- Documentation, traceability, dependencies, and anomaly records are updated.
