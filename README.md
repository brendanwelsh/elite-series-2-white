# elite-series-2-white

> A **white** recolor of the Xbox **Elite Series 2 Core** controller skin for
> [gamepadviewer.com](https://gamepadviewer.com) — sticks tilt, triggers compress, and buttons light
> up live as you play. White body, black diamond grips, just like the real Core.

![Preview](preview.png?raw=true "Xbox Elite Series 2 White skin preview")

## What it is

An on-screen white Elite Series 2 Core controller that reflects live gamepad input — sticks tilt,
triggers/bumpers compress, face buttons and d-pad highlight on press. Every button is visible at rest;
press feedback is an overlay, not a hide/show.

It's a fork of [Cinzya/xbox-elite2-skin](https://github.com/Cinzya/xbox-elite2-skin) (the black Elite
skin), recolored to the Core's two-tone look: white body and buttons, black diamond-textured grips.

## How to use

On [gamepadviewer.com](https://gamepadviewer.com), paste this into the **custom CSS** field of the
URL-generation dialog:

```
https://brendanwelsh.github.io/elite-series-2-white/elite2.css
```

## How the recolor works

`scripts/recolor-white.ps1` (PowerShell + System.Drawing, no dependencies) recolors the original assets:

- **Inverted to white:** `A/B/X/Y`, `Start/Select`, both `Bumper`s, both `Trigger`s.
- **Left untouched:** `Stick Left/Right` (already black-topped, matches the Core), `dpad` (already
  grayscale), all `F-*` fightstick assets.
- **Polygon-masked invert** for `base.png` / `base-disconnect.png`: the body region flips black→white
  while the diamond-grip area stays black.

The body polygon is defined at the top of `recolor-white.ps1` — adjust the vertices and re-run to change
the grip/body split.

## Regenerate

```powershell
powershell.exe -ExecutionPolicy Bypass -File scripts/recolor-white.ps1
powershell.exe -ExecutionPolicy Bypass -File scripts/build-preview.ps1
```

## Credit

- Original skin: [Cinzya/xbox-elite2-skin](https://github.com/Cinzya/xbox-elite2-skin)
- Gamepad viewer: [gamepadviewer.com](https://gamepadviewer.com) (mrmcpowned)

## Related

- **[playstation-ds5-white](https://github.com/brendanwelsh/playstation-ds5-white)** — the same
  white-controller treatment for the PS5 DualSense.

## Disclaimer

Unofficial fan recolor; no affiliation with Microsoft or Xbox.
