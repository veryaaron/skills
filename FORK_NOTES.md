# Fork notes

Forked from [peterdrier/skills](https://github.com/peterdrier/skills) at `d0b954b` (2026-09-23).

## Review

Every file was read before forking. No network code, telemetry, hooks, MCP servers,
hidden Unicode or encoded payloads. The two `spend.py` scripts import only the Python
standard library and only read local transcripts (optionally appending to a local log).
All GitHub activity the skills describe targets the user's own repo.

## Changes from upstream

- **create-issue**: pre-approved tools narrowed to read-only `gh` commands. Removed
  `gh api *` (any API call, including writes), `gh issue create *`, `WebFetch` (any URL)
  and `rm /tmp/*`; `Write` limited to `/tmp/issue-body.md`. Filing an issue now needs a
  permission prompt as well as the skill's own confirmation.
- **spend**: no longer prefers a `spend.py` shipped inside the current project, which
  would run code from whatever repo is checked out.
- **orch routing**: Fable is used only when the user asks for it by name in the session;
  the escalation ceiling is otherwise `opus-high`.
- **finish**: upstream author's personal paths (`memory/capture.md`, `reviews/daily/`,
  `routines/evening.md`) made optional.
- **context-cleanup**: removed the author's Syncfusion example.
- Marketplace renamed to `veryaaron`.

## Pulling upstream changes

`upstream` has push disabled. To review new upstream work before taking it:

    git fetch upstream
    git log -p main..upstream/main   # read it all before merging
    git merge upstream/main
