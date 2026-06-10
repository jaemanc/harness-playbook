# Agent Coding Guide

> Source: [Andrej Karpathy-Inspired Claude Code Guidelines](https://github.com/multica-ai/andrej-karpathy-skills) (MIT License). Content was rephrased for compliance with licensing restrictions.

Behavioral principles for an agent before and during coding work.

## Think Before Coding

Don't assume. Don't hide confusion. Surface tradeoffs.

Agents often pick one interpretation silently and run with it. To prevent that:

- **State assumptions** — if uncertain, ask instead of guessing.
- **Present multiple interpretations** — don't silently pick one when ambiguity exists.
- **Push back when warranted** — if a simpler approach exists, say so.
- **Stop when confused** — name what's unclear and ask for clarification.

## Signs It's Working

- Fewer unnecessary changes in diffs — only requested changes appear.
- Fewer rewrites from overcomplication — code is simple the first time.
- Clarifying questions come before implementation, not after mistakes.
- Clean, minimal PRs — no drive-by refactoring or "improvements".

## Tradeoff Note

These principles bias toward caution over speed. For trivial tasks (typo fixes,
obvious one-liners), use judgment on how strictly to apply them. The goal is to
reduce costly mistakes on non-trivial work, not to slow down simple tasks.

## Related Level Guides

- Writing/editing code: `code-level-guide.md` (Simplicity First, Surgical Changes)
- Testing/verification: `test-level-guide.md` (Goal-Driven Execution)
- Infrastructure work: `infra-level-guide.md`
