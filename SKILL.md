---
name: commit-smart
description: Analyze staged changes and prepare a meaningful Conventional Commit message based on the actual diff. Use when asked to create a smart or context-aware Git commit.
---

# Smart Commit

Prepare an accurate commit by inspecting the changes, identifying their purpose, and writing a concise message that explains the outcome and motivation.

## Workflow

### 1. Inspect repository state

Run `git status --short`, `git diff --stat`, and `git diff --cached --stat`. Review untracked files separately. Do not assume files are staged.

### 2. Decide what belongs in the commit

If nothing is staged, show the changed files and propose a logical group. Ask before staging unless the user has already authorized staging. Use explicit paths or patch staging. Do not stage the entire working tree without checking its contents.

### 3. Analyze the staged diff

Read `git diff --cached`. Detect the type and scope from the actual changes. Common types include `feat`, `fix`, `refactor`, `perf`, `test`, `docs`, `build`, `ci`, and `chore`. Use a scope only when it names the primary affected module.

### 4. Compose the message

```text
type(scope): imperative summary

Explain why the change matters and any relevant context.
```

Use imperative wording, keep the subject specific and concise, avoid trailing punctuation, and respect project-specific conventions. Do not invent issue references or breaking changes.

### 5. Confirm and commit

Show the staged file list and proposed message. Obtain confirmation unless the user explicitly authorized committing this change. After committing, verify with `git log -1 --oneline` and `git status --short`.

## Safety

Never include secrets, credentials, local environment files, generated artifacts, or unrelated work. Do not amend commits, force-push, or rewrite history without explicit authorization.

## Final report

Provide the commit hash, final message, included files, and verification results. Be clear if the commit was not created.
