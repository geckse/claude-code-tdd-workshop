# Claude Code TDD Workshop

This repository is **boilerplate scaffolding** for Claude Code's skills, agents, and rules system. It contains no application code — the configuration here is project-agnostic and can be dropped into any codebase as a starting point.

## What's Here

### Workflow: Plan → Execute with TDD

The core flow is:

1. **`/plan`** — Invoke the `writing-plans` skill to turn a spec or requirements into a detailed implementation plan saved to `docs/plans/`. The plan **must** incorporate the `test-driven-development` skill — every task in the plan follows red-green-refactor: write the failing test, verify it fails, write minimal code to pass, verify it passes, then commit.
2. **Review** — The skill automatically dispatches a reviewer to validate the plan for completeness, TDD order, and actionability.
3. **Execute** — Choose between:
   - **Subagent-driven**: The `plan-executor` agent runs one task at a time in an isolated worktree, following strict TDD.
   - **Inline**: Execute tasks directly in the current session.

### Key Components

| Path | Type | Purpose |
|------|------|---------|
| `.claude/skills/writing-plans/` | Skill | Generates bite-sized implementation plans from specs |
| `.claude/skills/test-driven-development/` | Skill | Enforces red-green-refactor TDD discipline |
| `.claude/agents/plan-executor.md` | Agent | Executes a single plan task in an isolated worktree |
| `.claude/rules/example-rule.md` | Rule | Enforces plan file structure when editing `docs/plans/` |

### Principles

- **TDD is mandatory.** Failing test first, minimal implementation, verify green. No exceptions.
- **Plans are self-contained.** Every plan must be readable by a fresh agent with zero context.
- **Bite-sized steps.** Each step is 2-5 minutes: write test, run, implement, run, commit.
- **DRY / YAGNI.** No speculative abstractions. No duplicated logic.

## Adapting to Your Project

This is scaffolding. To use it in a real project:

1. Copy the `.claude/` directory into your repo
2. Replace this `CLAUDE.md` with project-specific instructions (tech stack, conventions, repo structure)
3. Customize skills and rules to match your workflow
4. Add project-specific agents as needed
