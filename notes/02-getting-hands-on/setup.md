# Claude Code Setup

> **Lesson:** Getting hands on → Claude Code setup
> **Date:** 2026-03-27

---

## Installation

```bash
# macOS (Homebrew)
brew install --cask claude-code

# macOS / Linux / WSL
curl -fsSL https://claude.ai/install.sh | bash

# Windows CMD
curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd
```

Full quickstart docs: https://code.claude.com/docs/en/quickstart

## First Run

```bash
claude
```

The first time you run this, Claude Code prompts you to authenticate via browser (OAuth).

## Special Setups

| Platform | Docs |
|----------|------|
| AWS Bedrock | https://code.claude.com/docs/en/amazon-bedrock |
| Google Cloud Vertex | https://code.claude.com/docs/en/google-vertex-ai |
