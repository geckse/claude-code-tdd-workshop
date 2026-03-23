# Claude Code TDD Workshop

A hands-on workshop for learning test-driven development with Claude Code's customization system — skills, agents, and rules.

This repo contains boilerplate scaffolding that demonstrates how to structure a `.claude/` directory to drive a plan-then-execute workflow with strict TDD. There is no application code; the configuration is project-agnostic and can be dropped into any codebase.

## What You'll Learn

- **Skills** — reusable prompt templates that define how Claude approaches specific tasks (planning, TDD)
- **Agents** — subagent definitions that execute work autonomously in isolated worktrees
- **Rules** — contextual instructions that activate automatically based on file paths

## Repository Structure

```
.claude/
├── skills/
│   ├── writing-plans/        # Generates implementation plans from specs
│   └── test-driven-development/  # Enforces red-green-refactor TDD
├── agents/
│   └── plan-executor.md      # Executes plan tasks in isolated worktrees
└── rules/
    └── example-rule.md       # Enforces plan file conventions
```

## The Workflow

1. **Plan** — `/plan` turns requirements into a step-by-step implementation plan
2. **Review** — A reviewer validates the plan for completeness and TDD order
3. **Execute** — The `plan-executor` agent runs each task with strict TDD in an isolated worktree

## Attribution

This workshop is adapted as an exercise from a more complete example. The full reference implementation can be found at:

**[obra/superpowers — test-driven-development](https://github.com/obra/superpowers/tree/main/skills/test-driven-development)**
