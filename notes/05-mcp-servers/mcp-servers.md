# MCP Servers with Claude Code

> **Lesson:** MCP servers with Claude Code
> **Date:** 2026-03-29

---

## What is MCP?

**Model Context Protocol** — an open standard that lets Claude connect to external tools and data sources as plugins. They expose tools Claude can call just like its built-ins (Read, Bash, Grep, etc.).

```
Claude Code  →  MCP Server  →  External tool / service
                               (browser, database, API…)
```

## Installing a Server

Run this **in your terminal** (not inside Claude Code):

```bash
claude mcp add playwright npx @playwright/mcp@latest
#            ^^^^^^^^^^^ server name
#                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ command to start it
```

## Managing Permissions

By default Claude asks permission for each MCP tool call. To pre-approve a server, add it to `.claude/settings.local.json`:

```json
{
  "permissions": {
    "allow": ["mcp__playwright"],
    "deny": []
  }
}
```

Note the **double underscore** in `mcp__playwright`.

## Practical Example: Playwright

Playwright gives Claude a real browser, enabling workflows like:

1. Navigate to `localhost:3000`
2. Generate a component and inspect the visual output
3. Update the generation prompt based on what it actually sees
4. Test again with the improved prompt

This is more powerful than code review alone — Claude sees the rendered result, not just the source.

## Popular MCP Servers

| Server | Use Case |
|--------|----------|
| `@playwright/mcp` | Browser automation, visual testing |
| `@modelcontextprotocol/server-github` | GitHub API access |
| `@modelcontextprotocol/server-postgres` | Direct DB queries |
| `@modelcontextprotocol/server-filesystem` | Extended file operations |

## Notes

- MCP servers run locally or remotely and start on demand.
- They transform Claude from a code assistant into a full toolchain partner.

## Questions / Things to Explore

- [ ] Build a simple custom MCP server
- [ ] Try Playwright MCP on the uigen project
