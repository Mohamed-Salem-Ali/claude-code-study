# The Claude Code SDK

> **Lesson:** Hooks and the SDK → The Claude Code SDK
> **Date:** <!-- fill in when you watch -->

---

## What the SDK Enables

Run Claude Code **programmatically** — embed it in scripts, CI pipelines, or build your own AI agent on top of it.

## Installation

```bash
npm install @anthropic-ai/claude-code
```

## Basic Usage

```typescript
import { query } from "@anthropic-ai/claude-code";

const messages = [];

for await (const message of query({
  prompt: "Explain the architecture of this project",
  options: { maxTurns: 3 }
})) {
  messages.push(message);
  console.log(message);
}
```

## Key Options

| Option | Description |
|--------|-------------|
| `maxTurns` | Max tool-use rounds before stopping |
| `systemPrompt` | Override the system prompt |
| `tools` | Restrict which tools are available |
| `cwd` | Working directory for the session |

## Use Cases

- CI pipeline: auto-fix lint errors before merge
- Batch processing: run the same task on 50 files
- Custom agent: build a specialized coding assistant

## Notes

<!-- Your notes here -->
