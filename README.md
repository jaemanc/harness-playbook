# harness-playbook

A collection of general-purpose engineering guidelines for AI agents and vibe-coding sessions to reference.

## Purpose

This repo centralizes **general-purpose guidelines** that any agent or coding tool can follow consistently. It holds only principles that are reusable anywhere, not tied to a specific project or stack.

## Structure

All playbook files live under `.kiro/steering/`:

| File | Content |
|---|---|
| `git.md` | Git workflow rules (commit, push permissions) |
| `code-level-playbook.md` | Principles for writing and editing code |
| `test-level-playbook.md` | Principles for testing and verification |
| `infra-level-playbook.md` | Principles for infrastructure, IaC, and secrets handling |
| `agent-coding-playbook.md` | General behavioral principles for agents |

## Usage from Other Projects

To reference these playbooks from another project:

**Option A: Git Submodule (recommended)**

```bash
cd your-project
git submodule add https://github.com/your-org/harness-playbook .kiro/steering/harness-playbook
```

This places the playbooks under `.kiro/steering/harness-playbook/`. Your project can also have its own steering files alongside:

```
your-project/
├── .kiro/steering/
│   ├── harness-playbook/   ← submodule (shared rules)
│   │   ├── git.md
│   │   ├── code-level-playbook.md
│   │   └── ...
│   └── my-project-rules.md ← project-specific rules
```

**Option B: Symlink (local only)**

```bash
ln -s ~/path/to/harness-playbook/.kiro/steering/*.md your-project/.kiro/steering/
```

Good for local development. Not shareable via git.

**Option C: Copy via script**

```bash
curl -o .kiro/steering/code-level-playbook.md \
  https://raw.githubusercontent.com/your-org/harness-playbook/main/.kiro/steering/code-level-playbook.md
```

Good if you want to pin a specific version without submodule overhead.

**Note**: If your agent only reads flat files in `.kiro/steering/` (not subdirectories), you may need to copy or symlink the files to the steering root instead of using a submodule subfolder.

## Principles

- Write only guidelines that apply broadly.
- Keep out anything tied to a specific language, framework, or project.
