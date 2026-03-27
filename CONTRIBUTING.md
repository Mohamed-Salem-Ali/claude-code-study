# Contributing

Thanks for your interest in contributing! This is primarily a personal study workspace, but corrections, improvements, and additions are welcome.

## Ways to Contribute

- **Fix a mistake** — typos, broken commands, incorrect notes
- **Improve resources** — `resources/cheatsheet.md`, `resources/tips-and-tricks.md`
- **Add a template** — useful `CLAUDE.md` starters or custom commands under `templates/`
- **Suggest a lesson note improvement** — if a note is unclear or incomplete

## What to Avoid

- Changes to `projects/uigen/` unless fixing a reproducible bug (it's a third-party course project)
- Personal opinion rewrites of lesson notes — these are my study notes
- Large restructuring PRs without prior discussion via an issue

## Process

1. **Open an issue first** for anything beyond a small fix — describe what you want to change and why.
2. **Fork** the repo and create a branch from `main`:
   ```bash
   git checkout -b fix/typo-in-cheatsheet
   ```
3. Make your change. Keep it focused — one concern per PR.
4. **Submit a PR** using the provided template. Link the related issue.
5. PRs require at least one review before merging.

## Branch Naming

| Type | Pattern | Example |
|------|---------|---------|
| Bug fix / typo | `fix/<short-description>` | `fix/broken-setup-command` |
| New content | `add/<short-description>` | `add/hooks-cheatsheet-entry` |
| Update existing | `update/<short-description>` | `update/lesson-7-notes` |

## Commit Messages

Use the imperative mood, present tense:

```
fix: correct npm run setup command in cheatsheet
add: custom command template for /test
update: lesson 6 notes with GitHub Actions details
```

## Code of Conduct

Be respectful and constructive. This is a learning space.
