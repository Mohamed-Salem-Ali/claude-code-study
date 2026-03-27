# Adding Context

> **Lesson:** Getting hands on → Adding context
> **Date:** <!-- fill in when you watch -->

---

## Ways to Give Claude Context

| Method | How | Best For |
|--------|-----|----------|
| `CLAUDE.md` | Markdown file at project root | Permanent project facts |
| `@file` mention | Type `@filename` in prompt | One-off file reference |
| `/add-dir` | Add extra directory to context | Multi-repo work |
| Paste | Manually paste content | Quick one-time snippets |

## CLAUDE.md — What to Put In It

```markdown
# Project: MyApp

## Architecture
- Next.js App Router, TypeScript, Tailwind CSS
- API routes in src/app/api/
- Database: Prisma + SQLite

## Key Conventions
- Components use PascalCase
- Server actions live in src/actions/
- Never commit .env

## Commands
- `npm run dev` — start dev server
- `npm test` — run Vitest suite
```

## Notes

<!-- Your notes here -->
