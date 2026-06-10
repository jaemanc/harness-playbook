# Infra Level Playbook

> Source: [Andrej Karpathy-Inspired Claude Code Guidelines](https://github.com/multica-ai/andrej-karpathy-skills) (MIT License). Content was rephrased for compliance with licensing restrictions.

Applying the core principles to infrastructure and IaC work.

## Surgical Changes for Infra

- State the blast radius before any change that touches live resources.
- Modify only the requested resources; leave unrelated configuration untouched.
- Follow the style and patterns of the existing infrastructure code.

## Goal-Driven Execution for Infra

- Check the current state first (plan/diff), then define how you'll verify the change.
- For hard-to-reverse actions (deletion, production deploys, permission changes), get confirmation before executing.
- Prefer non-destructive alternatives where possible.

## Think Before Coding for Infra

- State your assumptions about the environment (dev/staging/prod); ask when unsure.
- Surface cost, security, and availability tradeoffs.
- Always flag exposed endpoints that lack authentication or access control.

## Secrets & Sensitive Data

Never let secrets or sensitive data leak into the repo, logs, or output.

Keep them out of version control:
- Never commit secrets: API keys, tokens, passwords, private keys, connection strings.
- Never commit `.env` files or credential files. Keep them in `.gitignore`.
- Commit a `.env.example` with key names only and no real values.
- Stage files explicitly instead of `git add .` to avoid sweeping in secret files.
- Before committing, flag any file likely to hold secrets (`.env`, `*.pem`, `credentials*`, `*.key`) and confirm it should be tracked.

Mask security-critical information:
- Reference secrets by key name, not value. Don't echo secret values back in chat, logs, or error messages.
- Redact sensitive values in examples and sample data (e.g. `API_KEY=***`).
- Use generic placeholders for credentials in docs and code samples.
- When reading a file that may contain secrets, avoid reprinting its contents verbatim.

Inject at runtime, not in code:
- Load secrets from environment variables or a secrets manager, never hardcode them.
- Pin and review dependencies so secrets can't be exfiltrated by untrusted packages.
