# Projects Workspace

This directory is a workspace for managing technical design document projects. Each subdirectory is a self-contained project.

## Conventions

- **Each project** is a subdirectory containing:
  - `AGENTS.md` — Agent behavioral instructions scoped to that project
  - `PROJECT.md` — Structured metadata (YAML frontmatter) with the project name, goal, status, and linked resources (Slack, Confluence, Jira, GitHub, etc.)
- **Project names** use kebab-case for directory names (e.g., `billing-redesign/`).
- **Status values** for projects: `draft`, `in-progress`, `in-review`, `finalized`, `archived`.

## Local Skills

Skills for managing this workspace are located in `.skills/`. When a user's request matches a skill trigger, read the corresponding `SKILL.md` and follow its instructions.

| Skill | Triggers | Description |
|-------|----------|-------------|
| `.skills/new-project/SKILL.md` | "new project", "create a project", "start a project" | Scaffold a new project directory with standard files |

## General Behavior

- When working inside a specific project directory, always read that project's `PROJECT.md` to understand its context, goals, and linked resources.
- When listing or summarizing projects, scan subdirectories for `PROJECT.md` files and read their frontmatter.
- Do not modify files in `.skills/` unless the user explicitly asks to update a skill.
