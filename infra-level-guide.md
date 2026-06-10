# Infra Level Guide

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
