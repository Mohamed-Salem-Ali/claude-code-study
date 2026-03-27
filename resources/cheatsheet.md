# Claude Code — Quick Reference Cheatsheet

---

## CLI Commands

```bash
# Start interactive session
claude

# One-shot task (non-interactive)
claude -p "your task here"

# Continue last conversation
claude --continue

# Resume specific conversation
claude --resume

# Print output only (no interactive UI)
claude -p "task" --output-format json
```

---

## In-Session Slash Commands

| Command | What It Does |
|---------|-------------|
| `/help` | Show all commands |
| `/clear` | Start a fresh conversation |
| `/compact` | Summarize conversation to save context |
| `/add-dir <path>` | Add another directory to context |
| `/model` | Switch model mid-session |
| `/cost` | Show token usage for this session |
| `/diff` | Show pending changes |
| `/undo` | Undo last file change |
| `/review` | (custom) Run code review |

---

## Context Tools

| Tool | Usage |
|------|-------|
| `@filename` | Reference a specific file |
| `@foldername/` | Reference a folder |
| `#symbol` | Reference a function/class by name |
| CLAUDE.md | Auto-loaded context for the project |

---

## Settings Files

| File | Scope |
|------|-------|
| `~/.claude/settings.json` | Global (all projects) |
| `.claude/settings.json` | Project-only |
| `CLAUDE.md` | Project guidance (read by Claude) |
| `.claude/commands/*.md` | Custom slash commands |

---

## Custom Commands

Create `.claude/commands/name.md` → use as `/name`

```markdown
# My Command Title
Prompt text goes here.
Use $ARGUMENTS to capture arguments from the user.
```

---

## Hooks (settings.json)

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [{ "type": "command", "command": "npm run lint" }]
      }
    ],
    "PreToolUse": [...],
    "Stop": [...]
  }
}
```

**Hook exit codes:**
- `0` → allow
- non-zero → block (PreToolUse only)

---

## MCP Servers

```bash
# Add a server
claude mcp add <name> -- <command>

# List servers
claude mcp list

# Remove a server
claude mcp remove <name>
```

---

## Permissions (settings.json)

```json
{
  "permissions": {
    "allow": ["Bash(npm run *)", "Edit(src/**)"],
    "deny":  ["Bash(rm -rf *)"]
  }
}
```

---

## Useful Flags

| Flag | Effect |
|------|--------|
| `--no-auto-approve` | Prompt for every tool call |
| `--dangerously-skip-permissions` | Skip all permission checks (use with care) |
| `--output-format stream-json` | Streaming JSON output for scripts |
| `--max-turns N` | Limit tool-use rounds |
