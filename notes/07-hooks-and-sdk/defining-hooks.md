# Defining Hooks

> **Lesson:** Hooks and the SDK → Defining hooks
> **Date:** <!-- fill in when you watch -->

---

## Hook Configuration

Hooks live in `settings.json` under the `"hooks"` key.

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "npm run lint --silent"
          }
        ]
      }
    ]
  }
}
```

## Matcher Patterns

- `"Edit"` — matches only the Edit tool
- `"Edit|Write"` — matches Edit or Write
- `"Bash"` — matches all Bash calls
- `""` (empty) — matches every tool

## Hook Input / Output

Hooks receive a JSON payload via stdin with tool details. They can:
- Exit `0` — allow the action
- Exit non-zero — **block** the action (for `PreToolUse`)
- Write JSON to stdout to pass data back

## Notes

<!-- Your notes here -->
