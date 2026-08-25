# FLY for Rhino — project instructions

First-person WASD navigation for Rhino 8 on **macOS**. Shipped as a single
Python file: the user drags `fly.py` onto the Rhino viewport, it copies
itself to a folder of their choosing and registers the `fly` and `flywasd`
commands. Nothing runs in the background after the flight window closes.

Solo project. Sold as is — see the licence note in `README.md`.

## Knowledge base

Long-lived findings live in `.claude/memory/`, versioned in git so every
machine sees the same notes. The index is imported below and loads every
session; open a topic file when you need the detail.

@.claude/memory/INDEX.md

Write new findings into the matching topic file and add one line to
`INDEX.md`. Conventions are in `.claude/memory/README.md`.

## Repository layout

```
CLAUDE.md            this file — loaded every session
README.md            user-facing docs (English, public)
ikona.png            product icon
fly.py               the plugin — NOT yet committed
.claude/
  settings.json      shared project settings
  SETUP.md           how to get this setup on a new machine
  memory/            versioned knowledge base
  rules/             path-scoped instructions
```

## Working rules

- **macOS only.** Rhino for Mac's Python is not the Windows one — do not
  reach for `Rhino.UI` dialogs, `System.Windows.Forms`, or anything
  Windows-flavoured. Check `.claude/memory/rhino.md` before adding an API.
- **One file ships.** `fly.py` must stay self-contained and installable by
  drag-and-drop. No package layout, no third-party dependencies.
- **Don't disturb Rhino's own navigation.** No intercepted gestures, and
  the camera target stays at a sane distance so orbiting still works after
  landing. This is a hard product constraint, not a preference.
- **Keep the key map in sync.** If keys change in `fly.py`, update the
  table in `README.md` in the same commit.
- English in the repo — README, code comments, commit messages.

## Testing

There is no automated test suite. Verification is manual, in Rhino 8 on
macOS (Apple Silicon): drag in the file, run `fly`, check movement, mouse
look, `ESC` release, and that orbiting still works after `quit`. Say
plainly when a change has only been reasoned about, not flown.
