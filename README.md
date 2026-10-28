<img src="ikona.png" width="120" alt="FLY">

# FLY for Rhino — macOS

Version 1.1 · October 2026 · for Rhino 8 on macOS

First-person navigation for Rhino 8 on macOS. Fly through your model with
WASD while looking around with the mouse, the way you would in a game.
FLY lives in a panel among Rhino's own panels, so it is always one word away.

## Install

1. Drag `fly.py` onto the Rhino viewport.
2. Rhino asks where you want to keep it. Confirm the suggested folder (or
   pick your own) and that is it.
3. The first time, FLY asks for the licence key from your order e-mail.
4. From now on, type **`fly`** in the command line — every time you start
   Rhino, no reinstalling.

The script copies itself to the folder you chose and registers the command
`fly`. Nothing else is installed into Rhino, and nothing runs in the
background once the flight ends.

## Use

Type **`fly`** and you are flying straight away. The FLY panel shows up among
Rhino's other panels — the tab with the blue plane. Drag the tab anywhere you
like; Rhino remembers the place.

| key | action |
|---|---|
| `W` `A` `S` `D` | move |
| `Q` `E` | down · up |
| `J` `L` `I` `K` | look |
| `M` | mouse look on / off (the cursor is captured while on) |
| `SHIFT` | boost |
| `ESC` | end the flight |

From `fly` until `ESC` the keys belong to FLY: clicking into a viewport or
onto a slider does not interrupt the flight, and nothing ends up in the
command line. `ESC` ends the flight, hands the keyboard back to Rhino and
hides the panel again if it was hidden before. Switching to another app
pauses the flight; click the box at the top of the panel to carry on.

`speed` sets the base speed; it starts scaled to the size of your model.
`look` sets how fast the view turns, for the mouse and the keys alike.
Both sliders are remembered until you close Rhino. `extents` frames the
whole model, `quit` does the same as `ESC`.

## Notes

Flying always starts from wherever the camera is, so you keep your place in the
model. Rhino's own navigation is untouched: no gestures are intercepted, and the
camera target is left at a sensible distance so orbiting still behaves after you
land. Tested on Rhino 8 for macOS on Apple Silicon.

FLY is sold as is, for the version it is built and tested for: Rhino 8 on macOS.
It is written and maintained by one person alongside other work, so updates for
later Rhino or macOS releases are at my discretion. See LICENSE.txt.

## Known macOS issue (not this plugin)

Rhino for Mac has a long-standing bug where two-finger trackpad drag starts
zooming instead of rotating the view. It is triggered by sleep, lid open, or
app switching, and it is unrelated to FLY. Restarting Rhino restores it. See
the McNeel forum for details.

## Support

Write to jan.havlica@gmail.com with your Rhino and macOS versions and what
happened. Your licence key works on up to 2 computers; if you hit the limit
after a reinstall, say so and I will reset it.

Anything to do with your order or payment — invoices, refunds — is handled by
Lemon Squeezy, the merchant of record for this sale.
