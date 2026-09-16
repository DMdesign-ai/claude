# Foil beta ticket

A holographic-foil "Thanks!" ticket with full pointer follow. Open `index.html` directly; there is no build step.

## What follows the pointer

The pointer is tracked over the whole page, not only over the card. Every value below eases toward its target each frame, so the card never snaps.

| Variable | Set on | Drives |
| --- | --- | --- |
| `--rx`, `--ry` | `.ticket-target` | 3D tilt, up to 15°, softly clamped so far-away pointers still lean the card |
| `--tx`, `--ty` | `.ticket-target` | A 10px drift toward the pointer and the drop shadow moving the other way |
| `--scale` | `.ticket-target` | A small lift while the pointer is inside the card |
| `--foil-x`, `--foil-y` | `.ticket` | Where the rainbow is brightest, the rim highlight, the foil text overlay, and the diffraction lines |
| `--foil-band-x`, `--foil-band-y` | `.ticket` | The specular band |
| `--rainbow-shift` | `.ticket` | Slides the holographic gradient against the movement |
| `--rainbow-angle` | `.ticket` | Points the gradient from the card centre toward the pointer |
| `--foil-active` | `.ticket` | 1 with the pointer inside, 0.6 elsewhere on the page, 0.35 at rest |

Inputs: mouse or pen anywhere on the page, touch drag, device tilt on phones (iOS asks permission on the first tap), and arrow keys when the ticket is focused. With `prefers-reduced-motion` the tilt and entrance animation are off and only the light moves.

## Swapping the assets

The three assets are inline SVG data URIs on `.ticket` so the file has no dependencies. Replace them with your own files the same way the original did:

```css
.ticket {
  --ticket-mask: url("/ticket-mask.svg");     /* any shape; white = visible */
  --ticket-mark: url("/ticket-mark.svg");     /* your logo, white on transparent */
  --foil-texture: url("/foil-texture.webp");  /* tileable grain */
}
```

The stub divider sits at 76.5% of the width (x = 306 in the 400 × 250 mask). Change `--stub` if you move it.

## Staff badge variant

`../badge/index.html` reuses the same surface layers and pointer loop as a portrait ID badge with a lanyard slot, portrait placeholder, security stripe, and ID footer. Edit the block marked "Edit these" in the markup for the name, role, department, and ID, and point `--badge-photo` on `.badge` at a photo. Drop the official wordmark in as an SVG in place of the text wordmark if you have it.
