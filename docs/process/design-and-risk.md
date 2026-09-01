# Design and Risk Integration

## Design records

Design must be sufficient for a competent person who did not author it to implement, review, maintain, and verify the system. Include as applicable:

- System context and trust boundaries.
- Component responsibilities and requirement allocation.
- Interfaces, schemas, units, protocols, and compatibility rules.
- Data flow, state transitions, concurrency, timing, and resource constraints.
- Error detection, fail-safe behavior, recovery, rollback, and degraded modes.
- Security architecture, identities, authorization, encryption, logging, updates, and vulnerability handling.
- Privacy classification, minimization, retention, deletion, and access controls.
- External services, SOUP/third-party software, suppliers, models, datasets, and operational assumptions.
- Deployment, migration, monitoring, service, and decommissioning considerations.

Design decisions that implement requirements or risk controls must be explicitly linked and reviewed.

## Risk-management integration

Apply the company risk-management procedure throughout the lifecycle. Software teams provide engineering evidence; authorized risk-management roles approve risk acceptability.

For each relevant hazard or security threat:

1. Identify the sequence of events and hazardous situation.
2. Estimate risk using the approved method.
3. Define risk controls in the required priority order.
4. Convert implemented controls into uniquely identified requirements.
5. Verify correct implementation and effectiveness.
6. Evaluate residual and overall residual risk through the authorized process.
7. Feed production and post-production information back into the analysis.

Do not use software warnings, documentation, or human review as substitutes for feasible design controls without documented justification.

## Agentic and AI considerations

When agents are used to develop conventional software, control provenance, permissions, untrusted input, nondeterministic output, and human review as described in `development-guidelines.md`.

If the delivered product itself contains an AI model or autonomous agent, explicitly design and verify:

- Intended task and prohibited actions.
- Model/provider/version and change policy.
- Training, evaluation, and production-data provenance and representativeness.
- Prompt/configuration/version control.
- Tool permissions, isolation, authorization, confirmation, and action limits.
- Protection from prompt injection, data exfiltration, unsafe tool use, and cross-user data exposure.
- Human oversight, override, escalation, and safe shutdown.
- Confidence/uncertainty handling and abstention criteria.
- Repeatability expectations, statistical acceptance criteria, and worst-case testing.
- Monitoring for drift, performance degradation, abuse, and emerging hazards.
- Fallback behavior during provider, network, model, or tool failure.

A narrative claim that a model is "generally accurate" is not an acceptable design control or acceptance criterion.

## Design review

Before Gate G2, reviewers confirm that approved requirements are allocated; risk controls are specified; safety/security architecture is coherent; interfaces and failure behavior are complete; third-party assumptions are controlled; and the planned verification can objectively demonstrate conformity.

Review findings remain open until the reviewer accepts their disposition. Agents cannot close their own safety- or compliance-relevant findings.
