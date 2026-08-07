# Architecture

## Purpose

Simulate an AI-assisted software development and outsourcing company with role-based agents across requirements, development, QA, DevOps, customer/project isolation, governance, and evidence traceability.

## Role model

### PM/BA Agent
Analyze requirements and draft user stories, acceptance criteria, tasks, and impact notes. Human approval remains required for material scope commitment.

### Developer Agent
Work inside the assigned project repository/workspace to prepare code, unit tests, lint/build results, and PR drafts. No autonomous merge to protected main branches and no production deployment.

### QA Agent
Generate and execute tests, analyze failures, and draft defects. QA does not self-approve release.

### DevOps Agent
Analyze pipelines/logs, perform approved sandbox/non-production diagnostics, and prepare build/deployment plans. Production changes require explicit human approval.

### Coordinator
Route work, enforce policy/project boundaries, and close evidence packages. Cross-customer context leakage is prohibited.

## Deterministic-first engineering

Prefer static analysis, linters, test runners, build tools, policy engines, scripts, and CI rules for deterministic engineering checks. Use agent reasoning for requirement interpretation, diagnosis, synthesis, trade-off analysis, remediation proposals, and other context-dependent work.

## Governed Tool / Integration Gateway

Git, ticketing, CI/CD, test runners, package/dependency tooling, infrastructure diagnostics, and MCP-style tools must be registered with owner, version, allowed roles, action scope, customer/project scope, credential scope, approval policy, audit log, and provenance rules.

## AI-Assisted DevSecOps flow

PR review and engineering operations should follow a controlled chain:

`static validation → tests → diff review → approval → commit/PR/deploy`

Diagnostics that could affect infrastructure are performed in sandbox/non-production environments first, with checkpoints before state-changing actions.

## Project isolation

Customer/project-specific repository, knowledge, memory, tasks, artifacts, and evidence stay inside the assigned workspace. Shared reusable skills must be reviewed and stripped of customer-specific data/secrets before promotion.

## Evidence lineage

Preserve traceability from requirement → task → prompt/model record → tool calls → code/diff → tests → approval → release/deployment artifact.
