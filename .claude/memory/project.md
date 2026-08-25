updated: 2026-08-25

# State of this repo

Seeded from `README.md`. Entries marked **[to verify]** were not confirmed
against code — confirm before relying on them.

## Repo contents

- 2026-08-25 — The repository holds only `README.md` and `ikona.png`. The
  README's install instructions point at `fly.py`, and the licence note
  points at `LICENSE.txt`; neither file is committed. Anyone following the
  README from a fresh clone cannot install the plugin.

## Product facts (from README)

- Registered commands: `fly` and `flywasd`.
- Install is drag-and-drop onto the Rhino viewport; the script copies itself
  to a folder the user picks and registers itself. Nothing else is written
  into Rhino, and nothing runs in the background once the window closes.
- Key map: `WASD` move · `Q`/`E` down/up · `JLIK` look · `M` mouse look
  (cursor captured, `ESC` releases) · `SHIFT` boost.
- In-flight commands: `speed` (base speed, initially scaled to model size),
  `extents` (frame the whole model), `quit` (end the flight).
- Flight starts from the current camera position, so the view is kept.
- Tested on Rhino 8, macOS, Apple Silicon.

## Positioning

- The competing walkthrough plugins (Stork, Walkie, the original Fly for
  Rhino) are Windows-only. macOS support is this project's whole reason to
  exist — it is the differentiator, not a nice-to-have.
- Sold as is by a solo developer. Fixes for later Rhino or macOS releases
  ship when there is time, with no promised schedule. Don't write support
  commitments into user-facing text.
