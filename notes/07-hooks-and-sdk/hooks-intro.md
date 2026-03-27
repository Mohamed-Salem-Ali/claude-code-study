# Introducing Hooks

> **Lesson:** Hooks and the SDK → Introducing hooks
> **Date:** <!-- fill in when you watch -->

---

## What Are Hooks?

Shell commands that Claude Code executes automatically in response to events in a session — before/after tool calls, on session start/stop, etc.

They run **outside** Claude's context window, so they are deterministic and not subject to Claude's judgment.

## Why Hooks?

- Enforce policies automatically (e.g., "always lint after editing")
- Log tool usage for audit trails
- Prevent dangerous commands from running
- Run tests after every file change

## Hook Events

| Event | Fires When |
|-------|-----------|
| `PreToolUse` | Before Claude calls any tool |
| `PostToolUse` | After a tool completes |
| `Stop` | When Claude finishes a response |
| `SubagentStop` | When a subagent finishes |

## Notes

<!-- Your notes here -->
