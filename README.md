# Claude Code in Action — Study Repository

> **Author:** [Mohamed Salem Ali](https://github.com/Mohamed-Salem-Ali)
> **Course:** [Claude Code in Action](https://www.anthropic.com/academy) — Anthropic Academy
> **Started:** 2026-03-27
> **Progress:** 9 / 21 lessons (42%)

---

## What This Repo Is

A structured workspace for studying the *Claude Code in Action* course — notes, exercises, experiments, and the course project (`uigen`) all live here.

If you're also taking this course, fork it and use it as your own study journal. If you're just curious about Claude Code, the `resources/` folder is a good starting point.

---

## Fork & Use This Repo

### Option 1 — Fork (recommended if you're taking the course)

1. Click **Fork** at the top-right of this GitHub page.
2. Clone your fork:
   ```bash
   git clone https://github.com/Mohamed-Salem-Ali/claude-code-study.git
   cd claude-code-study
   ```
3. Fill in your own notes as you watch each lesson.

### Option 2 — Clone (read-only / reference)

```bash
git clone https://github.com/Mohamed-Salem-Ali/claude-code-study.git
cd claude-code-study
```

### Setting Up the Course Project (`uigen`)

The `uigen` project requires Node.js 18+ and an Anthropic API key.

```bash
cd projects/uigen
cp .env.example .env          # then add your ANTHROPIC_API_KEY
npm run setup                 # install deps + Prisma migrate
npm run dev                   # starts on http://localhost:3000
```

> Without an API key the app still works — it falls back to a mock model that returns demo components.

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

---

## License

MIT — use freely, attribution appreciated.
