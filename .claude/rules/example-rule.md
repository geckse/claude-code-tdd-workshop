---
description: Applies when working with implementation plan files in docs/plans
paths:
  - docs/plans/**/*.md
---

# Plan File Rules

- Always follow the structure defined in the `writing-plans` skill (Goal, Non-Goal, Architecture, Tech Stack, Verification header)
- Use kebab-case for plan filenames with date prefix (e.g., `2026-03-23-user-authentication.md`)
- Every plan must be self-contained — assume it will be read by a fresh subagent with no other context
- Each task must list exact file paths (Create/Modify/Test) and include complete code, not placeholders
- Steps must be bite-sized (2-5 minutes) and follow strict TDD order: failing test → run → implement → run → commit
- Validation criteria must be concrete and testable (no vague phrases like "works well" or "looks good")
- Dispatch the `plan-executor` agent for subagent-driven execution, one task at a time
