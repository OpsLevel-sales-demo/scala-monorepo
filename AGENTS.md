# AGENTS.md

This file provides guidance for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these guardrails at all times:

### Protect Sensitive Data

- Do not read, log, print, or commit secrets, credentials, API keys, tokens, or passwords — even partially or in truncated form.
- Do not expose or transmit personally identifiable information (PII) or customer data.
- Do not add secrets or credentials to source files, configuration files, or test fixtures. Reference environment variable names only (e.g., `$SECRET_KEY`), never their values.
- Do not include sensitive data in commit messages, comments, or documentation.

### Prevent Unauthorized Deployments

- Do not push directly to `main`, `master`, or any production branch without explicit human approval.
- Do not trigger release pipelines, deploy workflows, or publish artifacts without explicit instruction.
- Do not modify CI/CD pipeline definitions (e.g., GitHub Actions workflows, Jenkins files) in ways that could cause unintended deployments.
- Do not bump version numbers or create release tags unless explicitly instructed.

### Avoid Destructive Operations

- Do not force-push (`git push --force`) to any branch.
- Do not delete branches, tags, or remote refs.
- Do not drop databases, tables, or data stores, and do not run irreversible migrations without explicit approval.
- Do not delete or overwrite infrastructure definitions (e.g., Terraform state, Kubernetes configs) without explicit instruction.
- Do not run commands that are difficult or impossible to reverse (e.g., `DROP TABLE`, `terraform destroy`, bulk deletes) without explicit human sign-off.
- Prefer additive, reversible changes over destructive ones wherever possible.
