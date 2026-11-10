# Sparkle GIF Maker

Make Y2K-style glitter text and sparkle GIFs in your browser, hosted at https://blinkie.siena.codes.

Type some text, pick a font and a glitter fill, scatter twinkles over it, and save a real animated GIF. Everything happens on the page itself. Nothing is uploaded, and there is no account or watermark.

## What it does

- Glitter fills in nine colors, plus rainbow glitter, chrome with a moving shine, and holographic.
- Twelve fonts, an outline, and a shadow, 3D extrude, or neon glow effect.
- Sparkles (twinkle, burst, star, heart, pixel, or a mix) scattered at random, only on the text, or wherever you click.
- Backgrounds: see-through, solid color, gradient, glitter, starry night, or your own photo.
- Size presets for a 400x200 banner, a square, an icon, a 468x60 web banner, an 88x31 button, and a 150x20 blinkie.

## Run it locally

It is one HTML file with no build step. Open it in a browser:

```bash
open index.html
```

Fonts come from Google Fonts, so they need a network connection. Everything else works offline.

## How the GIF gets made

The page draws every frame to a canvas, builds one 256-color palette shared by all frames using median cut, and writes the GIF89a file itself, LZW compression included. No GIF library is involved. The animation loops without a jump because every glitter flake and sparkle follows a sine wave that completes a whole number of cycles per loop.

## Deploys

Every push to `main` deploys to GitHub Pages through `.github/workflows/pages.yml`.
