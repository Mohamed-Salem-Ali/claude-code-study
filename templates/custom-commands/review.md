# Code Review

Review the recent changes in this project.

Run `git diff HEAD~1` to see what changed, then evaluate:

1. **Correctness** — Does the logic do what was intended?
2. **Security** — Any injection risks, exposed secrets, or auth bypasses?
3. **Edge cases** — What inputs or states could break this?
4. **Tests** — Are there tests covering the change? If not, note what should be tested.
5. **Style** — Does it follow the project's conventions from CLAUDE.md?

Format your review as a clear list of findings. Start with blockers, then suggestions, then minor notes.
