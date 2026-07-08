# dotfiles

Personal config files, tracked selectively from `$HOME`.

This repo uses a "deny by default" `.gitignore`: everything in the home
directory is ignored unless explicitly allowlisted. That keeps caches, app
state, personal files, and credentials out of version control.

## What's tracked

- `.gitconfig` — Git identity/config
- `.wslconfig` — WSL2 settings
- `.config/git/ignore` — global Git ignore rules
- `.claude/settings.json` — Claude Code settings (theme, etc.)

## Adding more

To track another file, add an explicit `!/path` rule to `.gitignore` rather
than removing the top-level `/*` deny. Directories need two rules: one to
un-ignore the directory itself, one to re-ignore its contents before
allowlisting specific files inside it (see the `.config` and `.claude`
blocks in `.gitignore` for the pattern).

Never allowlist credential or session-state files (e.g. `.claude.json`,
`.claude/.credentials.json`, `.ssh/id_*`).
