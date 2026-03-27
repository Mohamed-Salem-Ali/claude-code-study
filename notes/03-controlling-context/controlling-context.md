# Controlling Context

> **Lesson:** Controlling context
> **Date:** <!-- fill in when you watch -->

---

## Why Context Management Matters

Claude has a finite context window. Bloated context = slower responses + more cost + degraded quality.

## Strategies

| Strategy | When to Use |
|----------|-------------|
| `/clear` | Start a fresh conversation mid-session |
| `/compact` | Summarize long conversations to free space |
| Scoped `@mentions` | Only pull in files that are relevant |
| Small, focused tasks | Break big tasks into steps |

## What Eats Context Fast

- Large files (e.g., `package-lock.json`, generated code)
- Verbose tool output (long test runs, stack traces)
- Repeating the same context every turn

## Best Practice Pattern

```
1. Start with CLAUDE.md (permanent context)
2. @mention only the files relevant to this task
3. After big tool output → /compact before next prompt
4. One logical task per conversation
```

## Notes

<!-- Your notes here -->

## Questions / Things to Explore

- [ ] What does /compact actually preserve vs. drop?
- [ ] Is there a way to see current token usage?
