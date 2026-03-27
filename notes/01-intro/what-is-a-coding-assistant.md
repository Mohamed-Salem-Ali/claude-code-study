# What is a Coding Assistant?

> **Lesson:** Course Overview → What is a coding assistant?
> **Date:** 2026-03-27

---

## How Coding Assistants Work

When you give a coding assistant a task (e.g., fix a bug), it follows the same process a human developer would:

1. **Gather context** — understand the error, find the affected files
2. **Formulate a plan** — decide how to solve it
3. **Take action** — edit files, run commands, verify the fix

Steps 1 and 3 require interacting with the outside world (files, commands, docs).

---

## The Tool Use System

Language models alone can only process and return text — they cannot read files or run commands.

**How tool use solves this:**

| Step | Who Acts |
|------|----------|
| You send a request | You |
| Assistant appends tool instructions to the prompt | Assistant |
| Model responds with a tool call (e.g. `ReadFile: main.go`) | Model |
| Assistant executes the tool and sends results back | Assistant |
| Model gives a final answer using the results | Model |

The model never actually reads a file — it generates a formatted text request, and the assistant handles execution.

---

## Why Claude's Tool Use Matters

Claude (Opus, Sonnet, Haiku) is particularly strong at tool use compared to other models. This gives Claude Code three key advantages:

| Benefit | Why |
|---------|-----|
| **Tackles harder tasks** | Can chain tools together; adapts to tools it hasn't seen before |
| **Extensible platform** | Add new tools and Claude will use them automatically |
| **Better security** | Navigates codebases without indexing — your entire codebase isn't sent to external servers |
