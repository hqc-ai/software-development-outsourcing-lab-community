# Security Policy

This repository is a **Community reference/lab edition**, not a production deployment package.

## Never commit

- passwords, API keys, access tokens, SSH keys, private keys;
- customer source code or customer documents;
- production credentials or infrastructure configuration containing secrets;
- personally identifiable or confidential business data.

Use environment variables, local secret stores, or an enterprise secrets manager for experiments.

## Reporting a vulnerability

Please avoid publishing exploit details in a public issue when the issue could enable unauthorized access, cross-project leakage, destructive tool use, credential exposure, or unsafe agent actions. Contact the repository owner privately first and provide a concise reproduction and impact description.

## Community-lab assumption

Examples in this repository must be run in isolated test workspaces with non-production data. Any production deployment requires an independent security review, access-control design, logging/monitoring design, and organization-specific approval policy.
