# Exercises

Hands-on practice for each course section. Work here when a lesson gives you something to try.

---

## Structure

Each folder matches a course section:

```
exercises/
├── 02-getting-hands-on/   ← lesson 2 exercises
├── 03-controlling-context/
├── 04-custom-commands/
├── 05-mcp-servers/
├── 06-github-integration/
└── 07-hooks-and-sdk/
```

---

## How to Use

1. Read the lesson notes in `notes/XX-section/`
2. Complete the exercise in the matching folder here
3. Check off items in the notes' "Questions / Things to Explore" list

---

## Exercise Ideas by Section

### 02 — Getting Hands On
- [ ] Open `uigen` with Claude and ask it to explain the architecture
- [ ] Ask Claude to add a feature (e.g., character count to MessageInput)
- [ ] Intentionally break something and have Claude fix it

### 03 — Controlling Context
- [ ] Write a CLAUDE.md for uigen from scratch
- [ ] Practice `/compact` after a long diagnostic conversation
- [ ] Try a task using only `@mentions` (no CLAUDE.md)

### 04 — Custom Commands
- [ ] Create a `/review` command for uigen
- [ ] Create a `/test` command that runs the suite and summarizes failures
- [ ] Create a `/debug` command for a specific recurring issue

### 05 — MCP Servers
- [ ] Install Playwright MCP and test it on uigen's UI
- [ ] Explore what tools a GitHub MCP server exposes

### 06 — GitHub Integration
- [ ] Set up a Claude review action on this repo

### 07 — Hooks and SDK
- [ ] Write a PostToolUse hook that auto-lints after edits
- [ ] Write a PreToolUse hook that blocks editing `.env`
- [ ] Write a simple SDK script that runs a task on uigen
