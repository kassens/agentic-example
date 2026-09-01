# Canonical Repository Layout

This template separates executable product content, executable tests, reusable process instructions, and product-specific controlled records. A project may add technology-specific directories, but must preserve these boundaries or document an approved equivalent.

```text
/
├── AGENTS.md                  Agent policy and mandatory controls
├── CLAUDE.md                  Claude entry point importing AGENTS.md
├── README.md                  Project overview and navigation
├── src/                       Production source code
├── tests/                     Executable test code and non-production fixtures
│   ├── unit/                  Unit/software-unit tests
│   ├── integration/           Component and interface tests
│   ├── system/                End-to-end system tests
│   ├── verification/          Automated procedures used for formal verification
│   └── fixtures/              Synthetic, approved, non-production test data
├── config/                    Non-secret controlled product/runtime configuration
├── scripts/                   Reproducible build, analysis, test, and packaging scripts
└── docs/
    ├── process/               Reusable lifecycle instructions
    ├── templates/             Reusable controlled-record templates
    ├── reference/             Regulatory context and reference links
    └── project/               Product-specific controlled lifecycle records
```

Create only directories needed by the product. Git does not retain empty directories.

## Production source

Place released or potentially releasable software under `src/`, organized by product architecture rather than lifecycle phase. Generated source belongs under `src/generated/` only when it is part of the controlled build; record its generator, input, version, and regeneration method.

Do not put experiments, test helpers, verification scripts, credentials, raw evidence, or project-management documents under `src/`.

## Executable tests

Place test implementation under the matching `tests/` level. Each controlled test case has a project-prefixed `TC` ID and declares links to requirements and risk controls. Suggested naming is `<tc-id>_<short_description>`, adapted to language conventions, for example `test_aex_tc_0041_rejects_expired_token`.

- `tests/unit/`: isolated software-unit behavior; normally developer verification support.
- `tests/integration/`: component, database, service, device, and interface behavior.
- `tests/system/`: behavior of the integrated system in a representative environment.
- `tests/verification/`: executable formal procedures mapped to approved test-case specifications.
- `tests/fixtures/`: synthetic or properly approved datasets with provenance and version controls.

Test source is not an executed verification result. Results, logs, environment records, review, and approval belong with the `VER` record.

## Project-specific controlled records

Use the following structure under `docs/project/`, or maintain equivalent records in an approved external system and place an index/link file here:

```text
docs/project/
├── planning/                  Project plan, regulatory strategy references, baselines
├── requirements/             User, system, software, interface, security requirements
├── design/                   Architecture, detailed design, interfaces, decisions
├── risk/                     Risk-plan references, analyses, controls, reports
├── verification/
│   ├── protocols/            Approved test-case specifications and protocols
│   └── results/              Executed verification records and evidence indexes
├── validation/               Intended-use, usability, clinical/performance validation links
├── traceability/             Matrices, reports, and baseline coverage
├── changes/                  Change records and impact analyses
├── anomalies/                Defect/anomaly records and dispositions
└── releases/                 Release checklists, summaries, approvals, known anomalies
```

Requirements may be stored one per file, grouped in controlled specifications, or in an approved requirements-management system. Whatever the storage, stable IDs, revision history, approval state, and bidirectional traceability are mandatory.

## Evidence storage

Small, non-sensitive, reviewable evidence may be stored under `docs/project/verification/results/`. Large logs, screenshots, binaries, signed records, patient-related data, or evidence requiring immutability/access control should live in the approved evidence/QMS system. The repository record must link to it and record an identifier or checksum where appropriate.

Never commit protected health information, personal data, secrets, production database extracts, or uncontrolled third-party material as test data or evidence.

## Generated and transient content

Build output, caches, coverage output, temporary agent notes, local plans, and scratch artifacts belong in ignored build/temp locations. They are not controlled records and must not be cited as retained evidence unless deliberately captured through the approved verification process.

## Placement decision

- If it executes in the product: `src/`.
- If it executes to test the product: `tests/`.
- If it executes to build/analyze/package the product: `scripts/`.
- If it configures product behavior and contains no secret: `config/`.
- If it defines how all projects work: `docs/process/` or `docs/templates/`.
- If it records what this product requires, designed, tested, approved, or released: `docs/project/` or the indexed approved external system.
