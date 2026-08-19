---
name: new-project
description: Scaffold a new project directory with standard AGENTS.md and PROJECT.md files.
triggers:
  - new project
  - create a project
  - start a project
  - scaffold a project
inputs:
  - name: project_name
    description: Short kebab-case name for the project directory (e.g., "billing-redesign")
    required: true
  - name: description
    description: One-line description of what this project is about
    required: false
---

# new-project

Scaffold a new project in this workspace.

## Steps

1. **Get the project name.** If the user hasn't provided one, ask for it. The name should be kebab-case (lowercase, hyphens). If the user provides a display name, convert it to kebab-case for the directory and use the original as the title in `PROJECT.md`.

2. **Get a short description** (optional). If the user provides one, use it. If not, leave the `goal` field as `TODO`.

3. **Create the project directory** at `<workspace_root>/<project_name>/`.

4. **Create `PROJECT.md`** in the new directory with the following template:

    ```markdown
    ---
    name: "<Project Title>"
    goal: "<one-line goal or TODO>"
    status: draft
    created: <YYYY-MM-DD>
    resources:
      slack: []
      confluence: []
      jira: []
      github: []
      other: []
    ---

    # <Project Title>

    ## Overview

    <!-- Describe the project's purpose and scope -->

    ## Key Decisions

    <!-- Log important decisions as they are made -->
    <!-- Format: **YYYY-MM-DD** - Decision description -->

    ## Notes

    <!-- Working notes, thoughts, and context -->
    ```

5. **Create `AGENTS.md`** in the new directory with the following template:

    ```markdown
    # Project: <Project Title>

    This project is a technical design document workspace. Refer to `PROJECT.md` for structured metadata including goals, status, and linked resources.

    ## Behavior

    - When drafting or reviewing content for this project, always check `PROJECT.md` for the current list of resources and reference them as needed.
    - When the user adds new resources (Slack links, Confluence pages, Jira tickets, GitHub repos), update the `resources` frontmatter in `PROJECT.md`.
    - Keep the "Key Decisions" section in `PROJECT.md` up to date as decisions are made during the project.
    ```

6. **Confirm to the user** what was created and remind them to fill in `PROJECT.md` with relevant resources and details.
