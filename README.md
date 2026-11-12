# Smart Commit

A context-aware Git commit skill that analyzes staged changes and prepares meaningful Conventional Commit messages.

## Workflow

1. Inspect the working tree and staged state.
2. Identify the intended files and logical change boundary.
3. Read the staged diff and determine type and scope.
4. Write an imperative, concise commit subject.
5. Explain motivation in the body where useful.
6. Confirm before committing unless already authorized.
7. Verify the commit hash and remaining working tree state.

## Usage

Use when you want commit type and scope inferred from the actual diff rather than guessed from a short prompt. See `SKILL.md` for the full procedure and safety rules.
