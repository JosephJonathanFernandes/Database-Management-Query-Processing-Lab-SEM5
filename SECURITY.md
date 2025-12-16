# Security Policy

## Project Intent
- This is a learning/academic repository. Do not deploy the contents directly to production systems.
- Only use synthetic or anonymized data; never store or share real customer or personal data here.

## Reporting a Vulnerability
- Create a private issue with a concise description of the concern.
- Avoid sharing sensitive details or credentials in the issue body; request a secure channel if needed.
- If a secret was committed, rotate it immediately and propose a removal patch.

## Secrets and Credentials
- Do not commit API keys, passwords, connection strings, certificates, or `.env` files.
- Use placeholders in examples (e.g., `DB_USER=student`, `DB_PASS=changeme`).
- If a secret is found, remove it, rotate it, and document the mitigation in the PR.

## Safe Usage Guidelines
- Run scripts only in isolated development environments.
- Point scripts to disposable databases; never to production.
- Scrub outputs and logs before sharing to ensure no PII or secrets are included.

## Recommended Checks
- Run a secret scan (e.g., GitGuardian or `gitleaks`) before opening a PR.
- Review diffs for accidental credential leaks or sensitive data.
- Keep dependencies and database tooling up to date when possible.
