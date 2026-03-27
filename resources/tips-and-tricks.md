# Tips & Tricks — Getting the Most from Claude Code

---

## 1. Write a Good CLAUDE.md

This is the highest-leverage thing you can do. Claude reads it at session start — use it to describe:
- Tech stack and architecture
- Folder conventions
- Key commands (`npm run dev`, `npm test`)
- Things Claude should never do (e.g., "don't commit .env")

Keep it under ~200 lines. If it's too long Claude skims it.

---

## 2. One Task Per Conversation

Start a new conversation for each logical task. Mixed-purpose conversations degrade quality because Claude has to hold too much irrelevant context.

Bad: "Fix the login bug, then add dark mode, then update the README"
Good: Three separate sessions.

---

## 3. Be Specific About Location

Vague: "Add error handling"
Better: "In `src/lib/auth.ts` line 42, add try/catch around the JWT verify call and return null on failure"

The more specific you are about *where* and *what*, the fewer back-and-forth turns you need.

---

## 4. Give Acceptance Criteria

Tell Claude what "done" looks like:
- "The TypeScript compiler should pass with no errors."
- "The test `auth.test.ts` should pass."
- "The UI should match the screenshot I'll paste."

Claude will self-check against these criteria.

---

## 5. Use `/compact` Before Big Tasks

If you've had a long diagnostic session and now want Claude to implement something, run `/compact` first. This summarizes the conversation and frees up context for the actual work.

---

## 6. Reference Existing Patterns

"Follow the same pattern as `create-project.ts`" is often the best prompt you can write. Claude will read the reference file and mirror its style, error handling, and structure.

---

## 7. Hooks > Memory for Automation

If you want something to happen *every time* (lint, test, log), use a hook — not a prompt like "always run lint after edits." Prompts are suggestions. Hooks are guaranteed.

---

## 8. Custom Commands for Repetitive Tasks

Any prompt you type more than 3 times should become a custom command. Store it in `.claude/commands/` and it's a one-keystroke `/command` from then on.

---

## 9. Use `--continue` for Multi-Session Work

```bash
claude --continue
```
Picks up where you left off. Great for tasks that span multiple sittings.

---

## 10. Visual Input for UI Work

Paste screenshots or wireframes directly into the prompt. Claude Code is multimodal — it can read images and translate visual intent into code changes.

---

## 11. Use Extended Thinking for Hard Problems

For complex architectural decisions or tricky bugs, try:
```
Think carefully about this before responding...
```
or use `/think` if available. Extended thinking trades speed for quality.

---

## 12. Scope Permissions Tightly

In `settings.json`, use `allow` and `deny` to define exactly what Claude can touch. This is especially important for production environments.

```json
{
  "permissions": {
    "allow": ["Edit(src/**)", "Bash(npm run *)"],
    "deny":  ["Bash(git push *)", "Edit(.env)"]
  }
}
```
