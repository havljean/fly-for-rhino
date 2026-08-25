# Getting this setup on a new machine

Every device should end up with the same Claude Code setup and the same
project knowledge. Part of that travels in git, part is installed once per
machine.

You need a Claude Pro, Max, Team, or Enterprise subscription. The free plan
does not include Claude Code.

## 1. Install — the desktop app (no terminal needed)

This is the easy path. The desktop app **includes Claude Code**: no Node.js,
no CLI, no commands to type.

- macOS: <https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect>
- Windows: <https://claude.ai/api/desktop/win32/x64/setup/latest/redirect>
- Or the download page: <https://claude.com/download>

Run the installer, launch Claude from Applications, sign in, then click the
**Code** tab at the top. If Code asks you to upgrade, the account is on a
free plan.

The app runs the same engine as the terminal version and reads the same
config — `CLAUDE.md`, `.claude/settings.json`, `.claude/rules/`, skills. So
everything in this repo works identically in either one.

## 2. Get the project onto the machine

In the **Code** tab, pick **Local**, click **Select folder**, and choose a
folder to work in. Then just ask Claude in the prompt box:

```
Clone https://github.com/havljean/fly-for-rhino into this folder
and check out the branch claude/claude-app-folder-setup-9qqyck
```

Claude runs the git commands for you. Most Macs already have git; on Windows
install <https://git-scm.com/downloads/win> first, or local sessions won't
start.

Once the folder is open, `CLAUDE.md` and everything in `.claude/` load
automatically. Type `/context` and check **Memory files** to confirm.

## 3. Install — the terminal version (optional)

Only if you want the `claude` command in a terminal. Skip this section
otherwise; the two can also be installed side by side on the same project.

**Where the terminal is, if you have never opened it:**

- macOS: press `Cmd` + `Space`, type `Terminal`, press Enter. (Or Finder →
  Applications → Utilities → Terminal.)
- Windows: Start menu → type `PowerShell`. PowerShell is Windows-only —
  it does not exist on macOS or Linux.

macOS / Linux:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Or with Homebrew on macOS:

```bash
brew install --cask claude-code
```

Windows PowerShell:

```powershell
irm https://claude.ai/install.ps1 | iex
```

Then check it:

```bash
claude --version    # prints e.g. 2.1.245 (Claude Code)
claude doctor       # read-only diagnostics, starts no session
```

The native installer keeps the launcher at `~/.local/bin/claude` and the
versions under `~/.local/share/claude/versions/`, and auto-updates in the
background. Homebrew installs do not auto-update — run
`brew upgrade claude-code`.

## 4. What lives where

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

The last two are gitignored on purpose: that is the place for anything
machine-specific or private.

## 5. Two kinds of memory — the part that catches people out

Claude Code has a built-in **auto memory**: as you work it writes notes about
your preferences and corrections into `~/.claude/projects/<project>/memory/`
and loads the `MEMORY.md` index from there every session. Browse it with
`/memory`.

That directory is **machine-local**. It is not shared between your laptop,
another machine, or a cloud session — so it cannot be the answer to "the same
knowledge everywhere".

`.claude/memory/` in this repo is that answer: it is versioned, so `git pull`
gives every device the same notes. When auto memory picks up something on one
machine that matters everywhere, copy it into the matching topic file here
and commit it.

Auto memory is on by default. `.claude/settings.json` sets
`autoMemoryEnabled: true` explicitly so it stays on for this project whatever
your personal setting says. To move where it is stored, set
`autoMemoryDirectory` in a settings file to an absolute path or one starting
with `~/`.

## 6. Optional: the same personal setup everywhere

`~/.claude/CLAUDE.md` holds preferences that apply to all your projects on
that machine. It sits outside any repo, so it does not sync by itself. To
keep it identical on every device, store it in a private repo or a synced
folder and link it:

```bash
ln -s ~/dotfiles/claude/CLAUDE.md ~/.claude/CLAUDE.md
```

## Reference

- Desktop app: <https://code.claude.com/docs/en/desktop-quickstart>
- Terminal setup: <https://code.claude.com/docs/en/setup>
- Memory and CLAUDE.md: <https://code.claude.com/docs/en/memory>
