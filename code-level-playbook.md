# Code Level Playbook

Principles to apply when writing and editing code.

## 1. Simplicity First

Write the minimum code that solves the problem. Nothing speculative.

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If 200 lines could be 50, rewrite it.

Test: Would a senior engineer say this is overcomplicated? If yes, simplify.

## 2. Surgical Changes

Touch only what you must. Clean up only your own mess.

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match the existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it instead of deleting it.

When your changes create orphans:
- Remove imports, variables, and functions that your changes made unused.
- Don't remove pre-existing dead code unless asked.

Test: Every changed line should trace directly to the request.

## 3. Commit Discipline

Don't commit on your own. Confirm with the user first.

- Don't run commits unprompted.
- When a commit is needed, ask the user whether to commit.
- Show the proposed commit message and get confirmation before committing.
- Don't run `git commit` until the user approves.
