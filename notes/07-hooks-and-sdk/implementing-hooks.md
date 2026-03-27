# Implementing a Hook

> **Lesson:** Hooks and the SDK → Implementing a hook
> **Date:** <!-- fill in when you watch -->

---

## Example: Auto-lint on Edit

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          { "type": "command", "command": "npm run lint --silent" }
        ]
      }
    ]
  }
}
```

## Example: Block `rm -rf` in Bash

```python
#!/usr/bin/env python3
import json, sys

data = json.load(sys.stdin)
cmd = data.get("tool_input", {}).get("command", "")

if "rm -rf" in cmd:
    print(json.dumps({"decision": "block", "reason": "rm -rf is not allowed"}))
    sys.exit(1)
```

Save as `hooks/block-rm-rf.py`, then reference it:

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [{ "type": "command", "command": "python3 hooks/block-rm-rf.py" }]
      }
    ]
  }
}
```

## My Hook Implementations

- [ ] Auto-lint after edits
- [ ] Log all Bash commands to a file
- [ ] Block accidental `.env` edits

## Notes

<!-- Your notes here -->
