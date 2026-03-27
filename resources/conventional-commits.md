# Conventional Commits — Quick Reference

> Spec: [conventionalcommits.org](https://www.conventionalcommits.org)

## Format

```
<type>(<optional scope>): <short description>

[optional body]

[optional footer(s)]
```

## Types

| Type | When to use |
|------|-------------|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only changes |
| `style` | Formatting, missing semicolons — no logic change |
| `refactor` | Code change that is neither a fix nor a feature |
| `test` | Adding or fixing tests |
| `chore` | Build process, dependency updates, tooling |
| `perf` | Performance improvement |
| `ci` | CI/CD configuration changes |
| `revert` | Reverting a previous commit |

## Examples

```bash
feat: add custom /review command template
fix: correct npm run setup path in cheatsheet
docs: add lesson 7 hooks notes
chore: add .gitignore entry for .env files
feat(uigen)!: replace mock model with real API call
```

## Breaking Changes

Add `!` after the type, and/or add `BREAKING CHANGE:` in the footer:

```
feat!: rename API key env variable

BREAKING CHANGE: ANTHROPIC_KEY is now ANTHROPIC_API_KEY
```

## Scopes (this repo)

Use these optional scopes for clarity:

| Scope | Covers |
|-------|--------|
| `notes` | Files under `notes/` |
| `uigen` | Files under `projects/uigen/` |
| `resources` | Files under `resources/` |
| `templates` | Files under `templates/` |
| `exercises` | Files under `exercises/` |
| `ci` | `.github/` workflows |

## Rules

- Subject line: **imperative mood**, lowercase, no period at end
- Max 72 characters in subject line
- Body: explain *why*, not *what* (the diff shows what)
- One logical change per commit

## Why Conventional Commits?

- Machine-readable → auto-generate changelogs
- Clear intent at a glance in `git log`
- Enables semantic versioning (`feat` = minor bump, `fix` = patch, `!` = major)
