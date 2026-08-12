<img src="ikona.png" width="120" alt="FLY">

# FLY for Rhino — macOS

First-person navigation for Rhino 8 on macOS. Fly through your model with
WASD while looking around with the mouse, the way you would in a game.

Existing walkthrough plugins for Rhino (Stork, Walkie, Fly for Rhino) are
Windows-only. This one is built for macOS.

## Install

1. Drag `fly.py` onto the Rhino viewport.
2. Rhino asks where you want to keep it. Confirm the suggested folder (or
   pick your own) and that is it.
3. From now on, type **`fly`** in the command line — every time you start
   Rhino, no reinstalling.

The script copies itself to the folder you chose and registers the commands
`fly` and `flywasd`. Nothing else is installed into Rhino, and nothing runs
in the background once you close the window.

## Use

| key | action |
|---|---|
| `W` `A` `S` `D` | move |
| `Q` `E` | down · up |
| `J` `L` `I` `K` | look |
| `M` | mouse look (cursor is captured — press `ESC` to release) |
| `SHIFT` | boost |
| `ESC` | release mouse |

`speed` sets the base speed; it starts scaled to the size of your model.
`extents` frames the whole model, `quit` ends the flight.

## Notes

- Flight starts from wherever the camera is, so you keep your place.
- Rhino's own navigation is untouched: no gestures are intercepted, and the
  camera target is kept at a sane distance so orbiting still works after you
  land.
- Tested on Rhino 8, macOS (Apple Silicon).
- Sold as is, for Rhino 8 on macOS. I am a solo developer: fixes for later
  Rhino or macOS releases come when I have time, with no promised schedule.
  See LICENSE.txt.

## Known macOS issue (not this plugin)

Rhino for Mac has a long-standing bug where two-finger trackpad drag starts
zooming instead of rotating the view. It is triggered by sleep, lid open, or
app switching, and it is unrelated to this script. Restarting Rhino restores
it. See the McNeel forum for details.
