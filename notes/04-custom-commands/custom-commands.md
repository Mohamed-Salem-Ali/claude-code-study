# Custom Commands

> **Lesson:** Custom commands
> **Date:** <!-- fill in when you watch -->

---

## What Are Custom Commands?

Reusable slash commands (like `/review`, `/deploy`, `/test`) that you define once and run any time. They're markdown files that contain a prompt template.

## Where They Live

| Scope | Path | Available In |
|-------|------|--------------|
| Project-level | `.claude/commands/<name>.md` | This project only |
| Global | `~/.claude/commands/<name>.md` | All projects |

## Anatomy of a Command File

```markdown
# Review Code

Review the changes in the current branch.
Focus on:
- Security issues
- Performance regressions
- Missing tests

Run `git diff main` first to see what changed.
```

Save as `.claude/commands/review.md` → use as `/review`.

## Using `$ARGUMENTS`

```markdown
# Fix Issue

Fix GitHub issue #$ARGUMENTS.
Read the issue description, find the relevant code, implement the fix, and write a test.
```

Usage: `/fix 42`

## Notes

<!-- Your notes here -->

## My Commands to Build

- [ ] `/review` — code review checklist
- [ ] `/test` — run tests and summarize failures
- [ ] `/explain` — explain current file's architecture
