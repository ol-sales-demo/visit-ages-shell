# AGENTS.md

This file defines guidelines and guardrails for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow these rules at all times when working in this repository.

### Protect Sensitive Data

- Never read, log, print, or commit secrets, credentials, API keys, tokens, or passwords — even partially or in truncated form.
- Never hard-code sensitive values into source files, configuration files, or scripts. Reference environment variable names only (e.g., `$SECRET_KEY`).
- Do not access, copy, or expose personally identifiable information (PII) or customer data outside of the immediate task scope.
- Do not include sensitive data in commit messages, comments, or documentation.

### Prevent Unauthorized Deployments

- Do not push directly to `main`, `master`, or any production-tracking branch without explicit human approval.
- Do not trigger release pipelines, deploy workflows, or publish packages (e.g., `npm publish`, Heroku release commands) without explicit approval.
- Do not modify CI/CD configuration (e.g., files under `.github/workflows/`) in ways that would auto-deploy or bypass review gates.
- All changes intended for production must go through a pull request and be reviewed by a human before merging.

### Avoid Destructive Operations

- Do not force-push (`git push --force`) to any branch.
- Do not delete branches, tags, or remote refs.
- Do not drop, truncate, or irreversibly modify data or infrastructure (e.g., no destructive database migrations without an explicit rollback plan and human sign-off).
- Do not run commands that are difficult or impossible to reverse (e.g., removing Heroku add-ons, clearing caches that affect production) without explicit approval.
- Prefer reversible changes; when a destructive step is necessary, flag it clearly for human review before proceeding.
