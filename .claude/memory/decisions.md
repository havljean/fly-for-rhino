updated: 2026-08-25

# Decision log

Newest first. Record the decision, the reason, and what was rejected.

- 2026-08-25 — **macOS only, Windows out of scope.** Stork, Walkie and the
  original Fly for Rhino already serve Windows. Splitting effort across both
  platforms would remove the only reason to pick this plugin. Revisit only
  if the macOS version is stable and someone is asking to pay for Windows.

- 2026-08-25 — **Single-file, drag-and-drop install.** The plugin stays one
  Python file with no third-party dependencies, installed by dragging it
  onto the viewport. Rejected: a real Rhino plugin package, which would mean
  a build step, signing, and an install path for users who mostly want to
  try it in thirty seconds.

- 2026-08-25 — **Never intercept Rhino's own navigation.** Gestures and
  Rhino's native camera controls are left untouched. A walkthrough tool that
  degrades normal modelling navigation would not survive daily use.
