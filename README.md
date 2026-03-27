# Claude Code in Action — Study Repository

> **Course:** Claude Code in Action — Anthropic Academy
> **Started:** 2026-03-27
> **Progress:** 9 / 21 lessons (42%)

---

## What This Repo Is

A structured workspace for studying the *Claude Code in Action* course — notes, exercises, experiments, and the course project (`uigen`) all live here.

---

## Folder Structure

```
.
├── projects/
│   └── uigen/              # Course project (provided as zip in lesson 1)
├── notes/                  # Lesson-by-lesson notes
│   ├── 01-intro/
│   ├── 02-getting-hands-on/
│   ├── 03-controlling-context/
│   ├── 04-custom-commands/
│   ├── 05-mcp-servers/
│   ├── 06-github-integration/
│   └── 07-hooks-and-sdk/
├── exercises/              # Hands-on practice per section
├── experiments/            # Free sandbox — try anything
├── templates/              # Reusable CLAUDE.md, command templates
└── resources/
    ├── cheatsheet.md       # Quick-reference card
    └── tips-and-tricks.md  # Advice on getting the most from Claude Code
```

---

## Course Curriculum

| # | Section | Status |
|---|---------|--------|
| 1 | What is Claude Code? | ✅ Done |
| 2 | Getting hands on | ✅ Done |
| — | Course satisfaction survey | ✅ Done |
| 3 | Controlling context | ✅ Done |
| 4 | Custom commands | ✅ Done |
| 5 | MCP servers with Claude Code | ✅ Done |
| 6 | Github integration | ✅ Done |
| 7 | Hooks and the SDK | 🔲 Up next |
| 8 | Quiz & Summary | 🔲 Not started |

> Update status as you complete lessons. Use ✅ Done / 🔲 Not started / 🔄 In progress.

---

## How to Use This Repo

1. **After each lesson** — write notes in the matching `notes/XX-section/` file.
2. **For hands-on tasks** — work inside `exercises/XX-section/`.
3. **For free exploration** — use `experiments/` without worrying about breaking things.
4. **For reusable patterns** — save them in `templates/`.
5. **Reference** — `resources/cheatsheet.md` for quick commands.

---

## Quick Start — Claude Code

```bash
# Start Claude Code in any project folder
claude

# Start with a specific task
claude "explain the project structure"

# Non-interactive one-shot command
claude -p "add error handling to src/lib/auth.ts"
```

See `resources/cheatsheet.md` for the full command reference.
