# GitHub Integration

> **Lesson:** GitHub integration
> **Date:** <!-- fill in when you watch -->

---

## What the Integration Enables

- Automated PR reviews triggered by GitHub Actions
- Claude commenting on PRs with code feedback
- Issue-to-code workflows

## GitHub Actions Setup

```yaml
# .github/workflows/claude-review.yml
name: Claude Code Review

on:
  pull_request:
    types: [opened, synchronize]

jobs:
  review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run Claude Code Review
        uses: anthropics/claude-code-action@beta
        with:
          anthropic_api_key: ${{ secrets.ANTHROPIC_API_KEY }}
```

## How It Works

1. PR opened / updated → triggers workflow
2. GitHub Action runs Claude Code with the diff
3. Claude posts a review comment on the PR

## Notes

<!-- Your notes here -->

## Questions / Things to Explore

- [ ] Set up automated review on this repo
- [ ] Explore issue-triggered workflows
