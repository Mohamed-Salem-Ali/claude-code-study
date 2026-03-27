# Useful Hooks

> **Lessons:** Hooks and the SDK → Useful hooks! + Another useful hook
> **Date:** <!-- fill in when you watch -->

---

## Hooks Shown in the Course

<!-- Fill in from the lesson -->

## My Collected Useful Hooks

### Auto-run tests after file changes

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [{ "type": "command", "command": "npm test --run 2>&1 | tail -20" }]
      }
    ]
  }
}
```

### Log every Bash command

```bash
#!/bin/bash
# hooks/log-bash.sh
INPUT=$(cat)
CMD=$(echo "$INPUT" | python3 -c "import sys,json; print(json.load(sys.stdin)['tool_input']['command'])")
echo "[$(date '+%Y-%m-%d %H:%M:%S')] $CMD" >> .claude/bash-history.log
```

### Notify when Claude finishes a long task

```json
{
  "hooks": {
    "Stop": [
      {
        "matcher": "",
        "hooks": [{ "type": "command", "command": "echo 'Claude done' | notify-send -" }]
      }
    ]
  }
}
```

## Notes

<!-- Your notes here -->
