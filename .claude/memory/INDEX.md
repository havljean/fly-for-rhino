# Knowledge index

One line per note. Topic files hold the detail — open them on demand.

## project.md — state of this repo
- `fly.py` and `LICENSE.txt` are referenced by `README.md` but are not in the repo yet.
- Product constraints that must not regress: single-file install, Rhino's own navigation untouched.

## rhino.md — Rhino 8 / macOS platform notes
- Rhino for Mac ships CPython 3 via RhinoCode; Windows-only UI and .NET Forms APIs are unavailable.
- Known Rhino-for-Mac bug (not ours): two-finger trackpad drag zooms instead of rotating after sleep / lid open / app switch. Restarting Rhino restores it.

## decisions.md — decision log
- Target is Rhino 8 on macOS only; Windows is explicitly out of scope (Stork, Walkie and the original Fly already cover it).

## workflow.md — how this project is worked on
- Dev machine is Ubuntu 26.04; Rhino has no Linux build, so nothing written here can be flown locally.
- No automated tests; verification is a manual flight in Rhino 8 on Apple Silicon.
- Development happens on `claude/*` branches, never directly on `main`.
