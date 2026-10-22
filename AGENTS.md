# AGENTS.md

This file provides guidance for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these guardrails at all times when working in this repository.

### Protect Sensitive Data

- Do not read, log, print, or commit secrets, API keys, tokens, passwords, or credentials. This includes values stored in environment variables (e.g., `DATABASE_URL`, `SECRET_KEY_BASE`, Heroku config vars).
- Do not hardcode sensitive values into source files, configuration files, or comments.
- Do not expose personally identifiable information (PII) or customer data in logs, diffs, or code changes.
- If a secret is accidentally exposed in a diff or output, stop immediately and do not proceed until the secret is rotated.

### Prevent Unauthorized Deployments

- Do not push code to production branches (e.g., `main`, `master`, `heroku`) or trigger Heroku deployments without explicit human approval.
- Do not run `git push heroku` or any command that deploys to a live environment unless explicitly instructed to do so in the current task.
- Do not trigger release pipelines, CI/CD workflows, or Heroku review app creation without explicit approval.
- Do not modify Heroku config vars, pipeline settings, or add-on configurations in a live environment without explicit instruction.

### Avoid Destructive Operations

- Do not force-push to any branch (`git push --force`).
- Do not delete branches, tags, or releases.
- Do not drop databases, remove data, or run irreversible migrations without explicit instruction and confirmation.
- Do not run commands that remove or overwrite application state in a way that cannot be undone (e.g., `heroku pg:reset`, `heroku restart` in production).
- Prefer reversible changes. When in doubt, make a change in a feature branch and request human review before merging.
