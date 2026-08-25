---
paths:
  - "**/*.py"
---

# Python rules for this project

- `fly.py` is the shipped artefact. It must stay **one self-contained file**
  with no third-party imports — it is installed by dragging it onto the
  Rhino viewport, so there is no place for a dependency to come from.
- Target Rhino 8 on macOS. Do not add Windows-only APIs
  (`System.Windows.Forms`, Windows-only `Rhino.UI` dialogs). If unsure
  whether an API exists on Mac, check `.claude/memory/rhino.md` and record
  the answer there.
- The install path writes the script to a user-chosen folder and registers
  the `fly` / `flywasd` commands. Anything that writes elsewhere in Rhino,
  or leaves something running after `quit`, breaks a promise made in
  `README.md`.
- Keep the key map and the in-flight commands (`speed`, `extents`, `quit`)
  in step with the table in `README.md`.
- There is no test runner. Changes are verified by flying the model by hand;
  don't claim a change is tested when it has not been run in Rhino.
