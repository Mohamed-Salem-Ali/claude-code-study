# Custom Commands

> **Lesson:** Custom commands
> **Date:** 2026-03-29

---

## What Are Custom Commands?

Reusable slash commands (like `/audit`, `/write_tests`) that you define once as markdown files. The filename becomes the command name.

## Setup

```
.claude/
└── commands/
    ├── audit.md        → /audit
    └── write_tests.md  → /write_tests
```

> After creating a new command file, **restart Claude Code** for it to be recognized.

## Where They Live

| Scope | Path | Available In |
|-------|------|--------------|
| Project-level | `.claude/commands/<name>.md` | This project only |
| Global | `~/.claude/commands/<name>.md` | All projects |

## Example: Audit Command

```markdown
Run `npm audit` to find vulnerable packages.
Run `npm audit fix` to apply updates.
Run the test suite to verify nothing broke.
```

Saved as `.claude/commands/audit.md` → run with `/audit`.

## Using `$ARGUMENTS`

The `$ARGUMENTS` placeholder lets commands accept input at run time.

```markdown
Write comprehensive tests for: $ARGUMENTS

Testing conventions:
- Use Vitest with React Testing Library
- Place test files in `__tests__/` next to the source file
- Name files `[filename].test.ts(x)`
- Use `@/` prefix for imports

Cover: happy paths, edge cases, error states.
```

Usage: `/write_tests the use-auth.ts file in the hooks directory`

Arguments can be anything — file paths, feature names, issue numbers, free-form instructions.

## Key Benefits

| Benefit | How |
|---------|-----|
| Automation | Multi-step workflows in one command |
| Consistency | Same steps every time |
| Project context | Bake in your conventions once |
| Flexibility | `$ARGUMENTS` adapts to any input |

## Notes

- Commands live in `.claude/commands/` — same place as project-level context.
- Templates in `templates/custom-commands/` in this repo are ready-to-copy starters.

## My Commands to Build

- [ ] `/review` — code review checklist
- [ ] `/test` — run tests and summarize failures
- [ ] `/explain` — explain current file's architecture
