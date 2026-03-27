# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is a personal study workspace for the Anthropic Academy course **"Claude Code in Action"** (21 lessons). It is not a runnable application — it's a structured notebook of notes, exercises, templates, and experiments alongside the course project.

## Repository Layout

```
notes/XX-section/     ← lesson notes (fill in as lessons are completed)
exercises/            ← hands-on practice tasks per section
experiments/          ← free sandbox, disposable
templates/            ← reusable CLAUDE.md and custom command starters
resources/            ← cheatsheet.md and tips-and-tricks.md
projects/uigen/       ← course-provided Next.js project (see below)
```

Progress is tracked in `README.md` (the curriculum table). Notes files contain `<!-- fill in -->` placeholders that get populated as lessons are watched.

## Course Project: `projects/uigen/`

UIGen is the hands-on project provided in lesson 1. It has its own `CLAUDE.md` at `projects/uigen/CLAUDE.md` with full architecture notes — read that when working inside `uigen/`.

**Key commands (run from `projects/uigen/`):**

```bash
npm run setup          # install deps + Prisma generate + migrate
npm run dev            # dev server (Turbopack)
npm test               # Vitest suite
npx vitest run src/path/to/file.test.ts  # single test file
npm run lint           # ESLint
npm run db:reset       # wipe and re-migrate SQLite
```

Requires `ANTHROPIC_API_KEY` in `.env`. Without it the app uses a `MockLanguageModel` returning static demo components.

## Notes Convention

Each note file has a standard shape:
- Front-matter: lesson name + date placeholder
- Concept tables or code blocks
- A `## Notes` section for personal observations
- A `## Questions / Things to Explore` checklist

When helping fill in notes, match this structure and keep entries concise.

## Templates

- `templates/CLAUDE.md.template` — starter for any new project
- `templates/custom-commands/` — `/review` and `/explain` command starters; copy to `.claude/commands/` in a project to activate them
