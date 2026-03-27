# MCP Servers with Claude Code

> **Lesson:** MCP servers with Claude Code
> **Date:** <!-- fill in when you watch -->

---

## What is MCP?

**Model Context Protocol** — an open standard that lets Claude connect to external tools and data sources as if they were native tools.

Think of MCP servers as plugins: they expose tools that Claude can call just like its built-in tools (Read, Bash, Grep, etc.).

## Architecture

```
Claude Code
   ↓  (MCP client)
MCP Server  →  External service / tool
               (browser, database, Slack, GitHub…)
```

## Adding an MCP Server

```bash
# Add a server globally
claude mcp add <name> -- <command>

# Example: Playwright browser automation
claude mcp add playwright -- npx @playwright/mcp@latest

# List installed servers
claude mcp list
```

## Config Location

MCP servers are stored in:
- Global: `~/.claude/settings.json` under `"mcpServers"`
- Project: `.claude/settings.json`

## Popular MCP Servers

| Server | Use Case |
|--------|----------|
| `@playwright/mcp` | Browser automation, visual testing |
| `@modelcontextprotocol/server-github` | GitHub API access |
| `@modelcontextprotocol/server-postgres` | Direct DB queries |
| `@modelcontextprotocol/server-filesystem` | Extended file operations |

## Notes

<!-- Your notes here -->

## Questions / Things to Explore

- [ ] Build a simple custom MCP server
- [ ] Try Playwright MCP on the uigen project
