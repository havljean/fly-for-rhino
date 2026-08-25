# How this folder works

`.claude/memory/` is the project's knowledge base: things worth knowing in a
future session that are **not** obvious from reading the code.

It is committed to git on purpose. Claude Code's built-in auto memory lives
in `~/.claude/projects/<project>/memory/` and is machine-local — it does not
travel between your laptop, another machine, or a cloud session. This folder
does, because it rides along with the repository.

## What goes in

- Decisions and the reasoning behind them, especially ones already rejected.
- Platform traps: Rhino / macOS behaviour that cost time to discover.
- External references — forum threads, McNeel docs, issue links.
- Working preferences that keep coming up.

## What stays out

- Anything derivable from the code or from `git log`.
- Anything already stated in `CLAUDE.md`.
- Secrets, licence keys, customer data. This folder is versioned and may
  become public — treat it as published.

## Conventions

- One topic per file, lowercase filename, `.md`.
- Every file starts with `updated: YYYY-MM-DD`.
- Newest entry first inside a file, as a short bullet with the date.
- After editing a topic file, add or update its line in `INDEX.md`.
- `INDEX.md` is imported by `CLAUDE.md` and loads into **every** session:
  keep it to one line per note, and keep the whole file well under 200
  lines. Detail belongs in the topic file, not the index.

## Promoting a machine-local note

If Claude saved something useful to auto memory on one machine
(`/memory` → open the auto memory folder), and it matters on every machine,
copy it into the matching topic file here and commit it.
