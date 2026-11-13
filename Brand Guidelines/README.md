# Brand Guidelines

A formal, data-driven brand book for Have I Been Pwned, built using the
[ordinarynerds/brand-book](https://github.com/ordinarynerds/brand-book) methodology:
a single `brand.json` source of truth drives an 11-spread guidelines book and a
set of reusable design tokens. Nothing here is invented — every colour,
typeface and type size is measured from the existing Figma file
(`Pwned brand and website`) and the live haveibeenpwned.com site.

## Files

- **`brand.json`** — the source of truth. Name, mission, values, audience,
  7 semantic colour roles (with hex + OKLCH), typography scale, logo rules and
  voice/tone guidance. Update this file first; everything else derives from it.
- **`brand-book.html`** — the 11-spread guidelines book itself (landscape,
  1440×900 per spread). Self-contained aside from loading the Switzer webfont
  from Fontshare's CDN. Open directly in a browser, or print to PDF
  (landscape, no margins) for a shareable document.
- **`tokens.css`** — CSS custom properties generated from `brand.json`, ready
  to drop into the website or product codebase.
- **`tokens.json`** — the same tokens in a generic design-token JSON shape,
  for use in design tools or other token pipelines.

## What's in the book

1. Introduction
2. Mission & principles
3. Logo system — the symbol
4. Logo system — lockups, clear space & usage
5. Colour system — brand colours
6. Colour system — greyscale & semantic roles
7. Typography — Switzer specimen
8. Typography — type scale
9. Voice & tone
10. Applications — UI components
11. Closing

## Known gaps

- **Monospace typeface** isn't formalised in the existing Figma file. `tokens.css`
  falls back to the system monospace stack for API/code samples until a brand
  mono is chosen.
- Only logos already present in this repo (`Logos/`) are embedded in the book.
  If new lockups or colour variants are added to `Logos/`, update
  `brand-book.html` to match.

## Updating

1. Edit `brand.json` with the new value(s).
2. Update `tokens.css` / `tokens.json` to match.
3. Update the relevant spread(s) in `brand-book.html`.
4. Open `brand-book.html` in a browser and visually confirm the change before
   committing.
