# Getting this setup on a new machine

The point of this file: every device you work on should end up with the
same Claude Code setup and the same project knowledge. Part of that travels
in git, part of it has to be installed once per machine.

## 1. Install Claude Code

You need a Claude Pro, Max, Team, Enterprise, or Console account. The free
plan does not include Claude Code.

**Desktop app** (graphical, no terminal):
download it from <https://claude.com/download>.
Direct macOS build:
<https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect>

**Terminal** — this is what the project structure below is built for.

macOS / Linux / WSL:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Or via Homebrew on macOS:

```bash
brew install --cask claude-code
```

Windows PowerShell:

```powershell
irm https://claude.ai/install.ps1 | iex
```

Check it worked:

```bash
claude --version    # prints e.g. 2.1.245 (Claude Code)
claude doctor       # read-only diagnostics, no session started
```

The native installer keeps the launcher at `~/.local/bin/claude` and the
versions under `~/.local/share/claude/versions/`. It auto-updates in the
background; Homebrew installs do not — run `brew upgrade claude-code`.

## 2. Clone the project

```bash
git clone https://github.com/havljean/fly-for-rhino.git
cd fly-for-rhino
claude
```

That is the whole per-project setup. Everything in `.claude/` and the root
`CLAUDE.md` comes down with the clone, so a fresh machine starts with the
same instructions, the same rules, and the same knowledge base as every
other one. Run `/context` in a session and check **Memory files** to confirm
`CLAUDE.md` loaded.

## 3. What lives where

Committed to this repo — identical on every device:

```
CLAUDE.md               project instructions, loaded every session
.claude/settings.json   shared project settings
.claude/memory/         the knowledge base (INDEX.md is imported by CLAUDE.md)
.claude/rules/          path-scoped instructions, loaded when matching files are read
```

On the machine, not in git:

```
~/.claude/CLAUDE.md                        your personal preferences, all projects
~/.claude/settings.json                    your personal settings
~/.claude/projects/<project>/memory/       auto memory — Claude's own notes
.claude/settings.local.json                your settings for this project only
CLAUDE.local.md                            your notes for this project only
```

The last two are gitignored on purpose: they are the place for anything
machine-specific or private.

## 4. Two kinds of memory — the part that catches people out

Claude Code has a built-in **auto memory**: as you work, it writes notes
about your preferences and corrections into
`~/.claude/projects/<project>/memory/`, and loads the `MEMORY.md` index
there at the start of every session. Browse it with `/memory`.

That directory is **machine-local**. It is not shared between your laptop,
another machine, or a cloud session — so it cannot be the answer to "the
same knowledge everywhere".

`.claude/memory/` in this repo is the answer to that: it is versioned, so
`git pull` gives every device the same notes. When auto memory picks up
something on one machine that matters everywhere, copy it into the matching
topic file in `.claude/memory/` and commit it.

Auto memory is on by default. `.claude/settings.json` sets
`autoMemoryEnabled: true` explicitly so it stays on for this project
regardless of your personal setting. To move where it is stored, set
`autoMemoryDirectory` in a settings file to an absolute path or one
starting with `~/`.

## 5. Optional: same personal setup everywhere

`~/.claude/CLAUDE.md` holds preferences that apply to all your projects on
that machine — it is outside any repo, so it does not sync by itself. If you
want it identical on every device, keep it in a private repo (or a synced
folder) and symlink it:

```bash
ln -s ~/dotfiles/claude/CLAUDE.md ~/.claude/CLAUDE.md
```

## Reference

- Setup and install: <https://code.claude.com/docs/en/setup>
- Memory and CLAUDE.md: <https://code.claude.com/docs/en/memory>
- Settings: <https://code.claude.com/docs/en/settings>
