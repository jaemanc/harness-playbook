# Test Level Playbook

> Source: [Andrej Karpathy-Inspired Claude Code Guidelines](https://github.com/multica-ai/andrej-karpathy-skills) (MIT License). Content was rephrased for compliance with licensing restrictions.

Principles for confirming goals through tests and verification.

## Goal-Driven Execution

Define success criteria, then loop until verified.

Turn imperative tasks into verifiable goals:

| Imperative instruction | Goal-driven version |
|---|---|
| "Add validation" | "Write tests for invalid inputs, then make them pass" |
| "Fix the bug" | "Write a test that reproduces it, then make it pass" |
| "Refactor X" | "Ensure tests pass before and after" |

For multi-step tasks, state a brief plan first:

```
1. [Step] -> verify: [check]
2. [Step] -> verify: [check]
3. [Step] -> verify: [check]
```

Strong success criteria let the agent loop independently toward the goal.
Weak criteria like "make it work" force constant clarification.

Key: Don't dictate the steps. Give success criteria and let it reach them.
