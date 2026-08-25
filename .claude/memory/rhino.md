updated: 2026-08-25

# Rhino 8 / macOS platform notes

## Confirmed

- 2026-08-25 — **Trackpad zoom bug is not ours.** Rhino for Mac has a
  long-standing bug where a two-finger trackpad drag zooms instead of
  rotating the view. It is triggered by sleep, lid open, or app switching,
  and it happens without this plugin installed. Restarting Rhino restores
  normal behaviour. Documented in `README.md`; see the McNeel forum. Do not
  spend time "fixing" it, and don't let a bug report about it get filed
  against this plugin.

- 2026-08-25 — **Camera target distance matters after landing.** Rhino
  orbits around the camera target. If a flight leaves the target sitting on
  or very near the camera, orbiting afterwards feels broken. Keeping the
  target at a sane distance on exit is a shipped behaviour, called out in
  `README.md`.

## To verify

- Rhino 8 on macOS runs scripts through the ScriptEditor / RhinoCode stack.
  Confirm which interpreter `fly.py` actually targets before adding imports,
  and record the answer here. Windows-only UI stacks (`System.Windows.Forms`
  and friends) are not an option on Mac either way.
- Mouse capture on macOS: record here which API the `M` mode uses to capture
  and release the cursor, and any Ventura/Sonoma/Tahoe differences found.

## References

- McNeel Discourse forum — the trackpad bug thread.
