# Adding Context

> **Lesson:** Getting hands on → Adding context
> **Date:** 2026-03-27

---

## The /init Command

Run this when starting Claude in a new project for the first time:

```
/init
```

Claude analyzes the entire codebase and writes a `CLAUDE.md` file summarizing:
- Project purpose and architecture
- Important commands
- Critical files and coding patterns

**Tip:** When Claude asks permission to write files, press `Shift+Tab` to auto-accept all writes for the session instead of approving each one.

---

## The CLAUDE.md File

Included in **every** request you make — acts like a persistent system prompt for your project.

**Two purposes:**
1. Guides Claude through your codebase (architecture, commands, patterns)
2. Lets you give Claude specific custom instructions

### Three CLAUDE.md Locations

| File | Scope | Committed? |
|------|-------|-----------|
| `CLAUDE.md` | Project (shared) | Yes — shared with all engineers |
| `CLAUDE.local.md` | Project (personal) | No — your private customizations |
| `~/.claude/CLAUDE.md` | Global | N/A — applies to all projects on your machine |

---

## Adding Custom Instructions with `#`

Use the `#` command to enter **memory mode** — Claude edits your CLAUDE.md intelligently instead of overwriting it.

```
# Use comments sparingly. Only comment complex code.
```

Claude merges this into your CLAUDE.md automatically.

---

## File Mentions with `@`

Reference specific files inline in your prompt:

```
How does the auth system work? @auth
```

Claude shows matching files to choose from, then includes the selected file's contents in the request.

### @ in CLAUDE.md

You can also embed `@` references inside CLAUDE.md itself:

```markdown
The database schema is defined in @prisma/schema.prisma.
Reference it anytime you need to understand the data structure.
```

This makes the schema file's contents available in **every** request automatically — no need for Claude to search for it each time.

---

## Too Much Context is Bad

> Irrelevant context **decreases** Claude's performance. Only include what's needed for the current task.
