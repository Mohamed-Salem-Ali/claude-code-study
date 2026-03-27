# Making Changes

> **Lesson:** Getting hands on → Making changes
> **Date:** 2026-03-27

---

## Using Screenshots

Paste a screenshot directly into Claude with **`Ctrl+V`** (not Cmd+V, even on macOS).

Claude can read the image and make targeted changes to match what you're showing — ideal for UI work where "the button should move to the right" is faster to show than to describe.

---

## Planning Mode

For complex tasks that need broad codebase understanding before touching any code.

**Enable:** Press `Shift+Tab` twice (or once if already auto-accepting edits).

In Planning Mode, Claude will:
1. Read more files across your project
2. Create a detailed implementation plan
3. Show you exactly what it intends to do
4. **Wait for your approval** before making any changes

Use this when a task touches multiple files or you want to review the approach first.

---

## Thinking Modes

For tasks requiring deep reasoning rather than broad exploration. Gives Claude more tokens to reason with before responding.

| Mode | Reasoning Depth |
|------|----------------|
| `think` | Basic |
| `think more` | Extended |
| `think a lot` | Comprehensive |
| `think longer` | Extended time |
| `ultrathink` | Maximum |

Just include the phrase in your prompt: *"ultrathink before answering this"*

---

## Planning vs Thinking — When to Use Each

| Situation | Use |
|-----------|-----|
| Task touches multiple files | Planning Mode |
| Complex logic / algorithm | Thinking Mode |
| Hard bug requiring deep analysis | Thinking Mode |
| Multi-step feature implementation | Planning Mode |
| Both breadth and depth needed | Both |

> Both modes consume extra tokens — there's a cost trade-off.
