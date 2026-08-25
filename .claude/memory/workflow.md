updated: 2026-08-25

# How this project is worked on

- 2026-08-25 — **No automated tests.** Verification is a manual flight in
  Rhino 8 on macOS (Apple Silicon): drag the file in, run `fly`, check
  movement, mouse look, `ESC` release, and that orbiting still works after
  `quit`. When a change has only been reasoned about and not flown, say so
  rather than reporting it as verified.

- 2026-08-25 — **Branching.** Work happens on `claude/*` branches and is
  pushed there; `main` is not committed to directly. Pull requests are only
  opened when explicitly asked for.

- 2026-08-25 — **README is the product page.** It is what a buyer reads, so
  changes to keys, commands, or supported versions belong in the same commit
  as the code change that caused them.
