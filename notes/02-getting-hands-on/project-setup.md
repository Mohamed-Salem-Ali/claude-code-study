# Project Setup

> **Lesson:** Getting hands on → Project setup
> **Date:** 2026-03-27

---

## The Course Project: UIGen

A UI generation app where you describe React components in a chat and Claude generates live previews. Provided as `uigen.zip` in this lesson.

## Setup Steps

```bash
# 1. Extract uigen.zip, then:
cd uigen

# 2. Install dependencies + set up SQLite database
npm run setup

# 3. (Optional) Add Anthropic API key for real generation
#    Get a key at https://console.anthropic.com/
#    Then place it in .env:
ANTHROPIC_API_KEY=your_key_here

# 4. Start the dev server
npm run dev
```

> Without an API key the app still works — it generates static fake/demo components. The API key is only needed to use real Claude generation.

## Requirements

- Node.js installed locally
- (Optional) Anthropic API key for full functionality
