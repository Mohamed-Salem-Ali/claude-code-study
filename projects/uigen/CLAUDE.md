# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Install dependencies, generate Prisma client, run migrations
npm run setup

# Development server (with Turbopack)
npm run dev

# Build for production
npm run build

# Run tests
npm test

# Run a single test file
npx vitest run src/path/to/file.test.ts

# Lint
npm run lint

# Reset database
npm run db:reset
```

> **Note:** `NODE_OPTIONS='--require ./node-compat.cjs'` is injected automatically by all npm scripts — the `node-compat.cjs` shim patches Node.js globals needed by certain dependencies.

## Environment

Copy `.env.example` to `.env.local` and set `ANTHROPIC_API_KEY`. Without it, the app falls back to a `MockLanguageModel` that returns static demo components (Counter, Form, Card).

## Architecture

UIGen is a Next.js 15 App Router application. Users describe React components in a chat, Claude generates code via tool calls, and the result is shown in a live preview iframe.

### Request Flow

1. User submits a chat message → `POST /api/chat` (`src/app/api/chat/route.ts`)
2. The route calls Claude (via Vercel AI SDK) with two tools: `str_replace_editor` and `file_manager`
3. Tool call results are streamed back to the client
4. `FileSystemContext` (`src/lib/contexts/FileSystemContext.tsx`) intercepts tool calls and updates the virtual file system
5. `PreviewFrame` (`src/components/preview/PreviewFrame.tsx`) re-renders when files change

### Virtual File System

All files live in memory — nothing is written to disk. The file tree is a `Map<string, string>` (path → content) managed by `FileSystemContext`. On save/load, the entire map is serialized to JSON and stored in the `Project.data` column in SQLite.

### JSX Transformation & Preview

`src/lib/transform/jsx-transformer.ts` uses `@babel/standalone` to transpile JSX/TSX in the browser. The transformed code is bundled into blob URLs with an import map so components can `import React from 'react'` at runtime inside the iframe.

### AI Tools

Defined in `src/lib/tools/`:
- `str-replace.ts` — `str_replace_editor` tool: view, create, str_replace, insert operations on files
- `file-manager.ts` — `file_manager` tool: rename and delete

### Authentication & Persistence

JWT stored in HTTP-only cookies (`jose`, 7-day expiry). Auth logic in `src/lib/auth.ts`; server actions in `src/actions/`. Anonymous users are supported — projects are only persisted to SQLite when a user is signed in. The `Project` model stores serialized `messages` (chat history) and `data` (file system snapshot).

### Database

Prisma + SQLite. Schema at `prisma/schema.prisma`. Generated client at `src/generated/prisma` (not the default `node_modules` location). Run `npx prisma studio` to browse data.

### Key Path Alias

`@/*` → `./src/*` (configured in `tsconfig.json` and `components.json`)

## Code Style

Only add comments for code whose logic is not self-evident. Avoid restating what the code does.

## After Significant Changes

Run lint and build to verify nothing is broken, and fix any issues before finishing:

```bash
npm run lint
npm run build
```
