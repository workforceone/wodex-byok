# WODEX Brand Assets

Source: `logo_origin.png` (white brushstroke “W” on black, 1024×1024).
All assets are derived from a vector trace (`potrace`) + the original raster master.

## Vector (scalable — preferred for UI)
| File | Use |
|------|-----|
| `wodex-mark.svg` | `fill="currentColor"` — inherits text color, theme-agnostic |
| `wodex-mark-black.svg` | Black W, transparent bg — for light backgrounds |
| `wodex-mark-white.svg` | White W, transparent bg — for dark backgrounds |

## Raster marks (transparent background)
- `wodex-mark-black-{256,512,1024}.png` — black W (light bg)
- `wodex-mark-white-{256,512,1024}.png` — white W (dark bg)

## Square tiles (solid background)
- `wodex-square-black-*` — white W on black (original)
- `wodex-square-white-*` — black W on white (inverted / 反色)

## Rounded app-icon tiles
- `wodex-rounded-black-*`, `wodex-rounded-white-*` (iOS-style ~22.5% radius)

## Favicons & platform icons
- `favicon.ico` (16/32/48/64), `favicon-16x16.png`, `favicon-32x32.png` — white W on black (legible on any tab theme)
- `apple-touch-icon.png` (180, solid — iOS auto-rounds)
- `android-chrome-192x192.png`, `android-chrome-512x512.png`
- `wodex-maskable-512.png` — PWA maskable (safe-zone padded)
