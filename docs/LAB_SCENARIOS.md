# Lab Scenarios

Use only synthetic/non-production repositories and credentials.

## SDL-001 — Requirement to User Story
Customer request → PM/BA analysis → draft user story/acceptance criteria → human review.

## SDL-002 — Developer Agent Code + Unit Test
Approved task → branch/workspace → code proposal → unit tests → static checks → diff evidence.

## SDL-003 — QA Test Generation & Execution
Requirement/acceptance criteria → test cases → execution → failure analysis → defect draft.

## SDL-004 — DevOps Build / Deployment Preparation
Build/pipeline context → non-production build or diagnostics → deployment plan → approval gate.

## SDL-005 — Customer Isolation Test
Attempt controlled access from Customer A agent/workspace to Customer B data. Expected result: deny and log.

## SDL-006 — End-to-End Evidence Traceability
Requirement → task → implementation → tests → approval → staging/release artifact with complete lineage.

## SDL-007 — PR Review & Diff Gate
Proposed change → static validation → unit/integration tests → agent-assisted review → human diff review → PR/commit decision.

## SDL-008 — CI/CD Failure Triage
Feed failed pipeline logs to DevOps Agent; allow diagnosis and remediation draft; execute diagnostics only in approved sandbox/non-prod scope.

## SDL-009 — Dependency / Security Review
Analyze synthetic dependency changes and security findings; propose remediation; require policy gate before material update or release.
