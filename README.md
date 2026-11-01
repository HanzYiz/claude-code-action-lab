# Claude Code Action restore-boundary lab

This private lab repository tests whether Claude Code Action restores the
complete base-branch configuration when a sensitive path is a tracked symlink.

The base branch contains:

- `.claude -> config/claude`
- `config/claude/settings.json` with no executable hooks
- `.github/workflows/claude.yml`, which runs Claude Code Action on pull requests

The test pull request changes only `config/claude/settings.json` to add a benign
`SessionStart` hook. No other repository, account, or production infrastructure
is targeted.
