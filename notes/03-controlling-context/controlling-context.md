# Controlling Context

> **Lesson:** Controlling context
> **Date:** 2026-03-29

---

## Keyboard Techniques

### Escape — Interrupt
Press `Escape` to stop Claude mid-response. Use this when Claude starts heading in the wrong direction or takes on too much at once. Redirect immediately rather than waiting for it to finish.

### Escape + `#` — Fix Recurring Mistakes
When Claude keeps making the same error across conversations:
1. Press `Escape` to stop the current response
2. Press `#` to open the memory prompt and record the correct approach
3. Continue — Claude will apply it going forward

### Double Escape — Rewind
Press `Escape` twice to see your full message history and jump back to any earlier point. Useful after a long debugging detour: you keep Claude's codebase understanding but strip out the noisy back-and-forth.

---

## Commands

| Command | What it does | When to use |
|---------|--------------|-------------|
| `/compact` | Summarizes conversation history, keeping key knowledge | Switching to a related next task; long conversation with valuable context |
| `/clear` | Wipes conversation history completely | Switching to an unrelated task; current context would confuse Claude |

**Rule of thumb:** compact = keep the knowledge, lose the noise. clear = full reset.

---

## What Eats Context Fast

- Large files (`package-lock.json`, generated code)
- Verbose tool output (long test runs, stack traces)
- Debugging back-and-forth that's no longer relevant

---

## Notes

- These aren't just convenience features — they're essential for long sessions.
- Combining double-Escape rewind with `/compact` on the trimmed conversation is a powerful reset pattern.

## Questions / Things to Explore

- [ ] What exactly does `/compact` preserve vs. drop?
- [ ] Is there a way to see current token usage?
