# Software Development & Outsourcing Lab Community

**A community reference architecture for governed AI agents across software development and outsourcing workflows.**

Part of the **AI Agent Governance Lab Community series by HQC**.

This lab simulates an AI-assisted software company using role-based agents across requirements, development, QA, DevOps, project/customer isolation, human approval, evidence traceability, and controlled engineering operations.

> **Community Edition:** this repository shares selected architecture patterns, governance controls, SDLC lab scenarios, and reusable skeletons. It is not a production delivery platform and does not contain customer code, proprietary project data, production credentials, or private deployment configuration.

## Why this repo exists

In software outsourcing, an AI agent can touch requirements, repositories, tests, CI/CD, logs, infrastructure, and customer information. The primary challenge is therefore not only code generation: it is maintaining **project boundaries, least privilege, approval gates, evidence lineage, and controlled engineering changes**.

## Target architecture

```text
CUSTOMER / PRODUCT OWNER
          |
          v
      PM / BA AGENT
   Requirement / Planning
          |
     Human Review
          |
          v
   PROJECT WORKSPACE
          |
   +------+------+------+
   |             |      |
   v             v      v
DEV AGENT     QA AGENT  DEVOPS AGENT
   |             |      |
   +------+------+------+
          |
          v
    AGENT CONTROL PLANE
   Identity / RBAC / Policy
   Project Isolation / Logs
   Memory / Knowledge / Approval
          |
          v
  TOOL / INTEGRATION GATEWAY
          |
    +-----+------+
    |            |
    v            v
   TOOLS        MODELS
Git/CI/Test    Local/API
```

Hermes Agent may be used as a lab runtime, but the architecture is **framework-independent** and does not require Hermes as a production core.

## Architecture Delta 07/08/2026

| Delta | Applied pattern | Community effect |
|---|---|---|
| ADP-0708-01 | Deterministic Automation vs Agent Reasoning | Deterministic checks/scripts/tests first when the task is fully specified. |
| ADP-0708-02 | Governed MCP / Tool Integration Layer | Git, issue tracker, test runners, CI/CD, diagnostics, and integrations are registered and policy-scoped. |
| ADP-0708-03 | Risk-Based Action Approval | L0-L5 model separates read/draft/reversible/external/production/prohibited actions. |
| ADP-0708-X1 | AI-Assisted DevSecOps / Engineering Operations | Adds PR review, CI/CD failure triage, dependency/security review, sandbox diagnostics, checkpoints, and validation before commit/deploy. |

## Controlled engineering sequence

```text
Proposed change
     |
     v
Static validation
     |
     v
   Tests
     |
     v
 Diff review
     |
     v
Approval gate
     |
     +--> Commit / PR (within policy)
     |
     +--> Deploy to approved non-prod environment
     |
     +--> Production requires explicit approval
```

The sequence is intentionally evidence-producing: requirement → task → model/prompt record → tool calls → code/diff → tests → review → approval → release/deployment artifact.

## Role boundaries

| Role | Allowed community-lab work | Key restriction |
|---|---|---|
| PM/BA Agent | Requirement analysis, user story/task drafts, impact notes | No autonomous scope commitment |
| Developer Agent | Code suggestions, branches, unit tests, lint/build, PR draft | No autonomous merge to main or production deploy |
| QA Agent | Test cases/execution, failure analysis, defect draft | Cannot self-approve release |
| DevOps Agent | CI/CD analysis, build, sandbox/non-prod diagnostics and plans | Production action requires explicit approval |
| Coordinator | Routing, policy checks, evidence closure | No cross-customer context leakage |

## Customer / project isolation

```text
workspace/
  customer-a/
    knowledge/
    repo/
    tasks/
    agents/
    evidence/
  customer-b/
    knowledge/
    repo/
    tasks/
    agents/
    evidence/
  shared/
    approved-skills/
```

An agent assigned to one customer/project must not access another customer's code, documents, memory, artifacts, or evidence. Shared skills are allowed only after review and must not contain customer-specific secrets or data.

## Initial lab scenarios

- **SDL-001 — Requirement to User Story**
- **SDL-002 — Developer Agent Code + Unit Test**
- **SDL-003 — QA Test Generation & Execution**
- **SDL-004 — DevOps Build / Deployment Preparation**
- **SDL-005 — Customer A vs Customer B Isolation Test**
- **SDL-006 — End-to-End Human Approval & Evidence Traceability**
- **SDL-007 — PR Review + Static Validation + Diff Review**
- **SDL-008 — CI/CD Failure Triage in Sandbox**
- **SDL-009 — Dependency / Security Review**

## Repository structure

```text
software-development-outsourcing-lab-community/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
├── SUPPORT.md
├── CHANGELOG.md
├── docs/
│   ├── ARCHITECTURE.md
│   ├── COMMUNITY_SCOPE.md
│   ├── GOVERNANCE_CONTROLS.md
│   ├── LAB_SCENARIOS.md
│   ├── ROADMAP.md
│   ├── Architecture_Delta_Pack_07082026.md
│   └── Software_Development_and_Outsourcing_Lab_...docx
├── examples/
│   ├── action-policy.example.yaml
│   ├── project-boundary.example.yaml
│   └── tool-registry.example.yaml
└── assets/donate/
```

## Start here

1. Read [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).
2. Review [`docs/COMMUNITY_SCOPE.md`](docs/COMMUNITY_SCOPE.md).
3. Create at least two synthetic customer workspaces to test isolation.
4. Register only the minimum tools required for the selected scenario.
5. Apply L0-L5 action classification before any change.
6. Preserve evidence from requirement through validation and approval.

## Community vs production

Production use requires additional organization-specific controls, including enterprise IAM, secrets management, repository protection, code-owner policies, CI/CD protection, artifact signing, network isolation, production change management, monitoring, incident response, data-processing requirements, and customer contractual controls.

## Author / Project

**Nguyễn Đăng Quang — HQC Training Consultancy**  
AI Agent Governance Lab / Community architecture and practical governance experiments.

### Donate / Support the project

If this Community Edition is useful to your work, training, research, or consulting practice, you can support future public releases.

**Bank transfer (Vietnam / international transfer):**

- **Account number:** `0944659937`
- **Bank:** Shinhan Bank
- **Account holder:** `NGUYEN DANG QUANG`
- **SWIFT:** `SHBKVNVX`

**QR images:**

- Bank QR: [`assets/donate/bank-qr.png`](assets/donate/bank-qr.png)
- USDT QR: [`assets/donate/usdt-qr.png`](assets/donate/usdt-qr.png)

> QR image files are intentionally left for the repository owner to upload manually. If the image is not present yet, the link above may return 404 until it is added.


## License

MIT License. See [`LICENSE`](LICENSE).
