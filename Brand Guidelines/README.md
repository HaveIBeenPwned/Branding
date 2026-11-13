# Brand Guidelines

Brand guidance for Have I Been Pwned, using the
[ordinarynerds/brand-book](https://github.com/ordinarynerds/brand-book) methodology.
The book covers visual identity, positioning, audience needs and responsible communication about data breaches.

For questions about using the HIBP brand, visit [support.haveibeenpwned.com](https://support.haveibeenpwned.com).

## Files

- **`brand.json`** — the source of truth for positioning, colour roles, typography, logo usage, voice, communication and evidence.
- **`brand-book.html`** — the 19-spread book (1440×900 per spread). Open in a browser or print to PDF in landscape with no margins.
- **`assets/`** — local copies of the website logos, the repository's three logo forms, selected official merchandise images and recreated branded-title SVGs.
  Keep this folder with the HTML when sharing it.
- **`tokens.css`** and **`tokens.json`** — reusable colour, typography and layout values kept in sync with `brand.json`.

Switzer loads from Fontshare's CDN and requires a network connection.
The book and token files are maintained manually; there is no automatic generation pipeline.

## Website deployment

The `.github/workflows/pages.yml` workflow deploys this directory to GitHub Pages on every push to `main`.
It can also be run manually from the Actions tab.
Source files stay here; deployment copies this directory's contents into `_site/`,
copies `brand-book.html` to `index.html` and adds `.nojekyll`.
The homepage is served directly, without an HTML redirect.

1. In repository **Settings > Pages > Build and deployment**, select **GitHub Actions** as the source.
2. Push the workflow to `main` and confirm the Pages deployment succeeds in the Actions tab.
   Before configuring a custom domain, check `https://haveibeenpwned.github.io/Branding/`
   and `https://haveibeenpwned.github.io/Branding/brand.json`.
3. When ready to use the production domain, set **Custom domain** in GitHub Pages to `branding.haveibeenpwned.com` and save.
4. In Cloudflare DNS for `haveibeenpwned.com`, create a **CNAME** named `branding`
   targeting `haveibeenpwned.github.io`, initially set to **DNS only** (grey cloud).
   The target must not include `https://` or a repository path.
5. Wait for GitHub's DNS check and certificate provisioning, then enable **Enforce HTTPS** in GitHub Pages.
6. Verify `https://branding.haveibeenpwned.com/` and `https://branding.haveibeenpwned.com/brand.json`.
   In the browser's Network panel, reload and check that images and the Fontshare stylesheet/fonts load successfully.
   Also check `/tokens.css`, `/tokens.json` and `/assets/Hero.svg`.

The custom domain is managed natively in GitHub Pages settings; this Actions deployment does not need a `CNAME` file.
Leave it unset until the initial GitHub Pages URL has been checked.
Relative asset paths support both the repository URL and the custom-domain root.
Once the custom domain is enabled, GitHub Pages redirects the default repository URL to it.

## What's in the book

1. Introduction
2. Mission & principles
3. Logo system — the symbol & live loading animation
4. Logo system — icon geometry & construction lines
5. Logo system — three forms & their contexts
6. Logo system — lockups, clear space & usage
7. Brand expression — other words & titles
8. Colour system — brand colours & gradients
9. Colour system — greyscale & semantic roles
10. Typography — Switzer specimen
11. Typography — type scale & responsive numbers
12. Voice & tone
13. Applications — UI components
14. Merchandise — the three forms in use
15. Merchandise — tonal, patterned & slogan treatments
16. Positioning — audience & naming guidance
17. Communication — results, notifications & privacy
18. Trust — evidence, attribution & sponsorship
19. Closing

## Basis and limits

Reviewed on **13 November 2026**.
Visual references combine existing brand assets with sampled public website usage.
They are not an exhaustive inventory of production CSS.
Editorial principles are formalised from the research, not claimed to be previously approved policy.
Public-perception research is qualitative, not a representative audience survey.

The research draws on HIBP's homepage, About, pricing, Passwords, FAQ, privacy and partner pages,
plus NCSC and NIST guidance, DOJ Qakbot resources, Consumer Reports (2022) and ABC (2023).
The complete source URLs are recorded in `brand.json` under `evidence`.
Older coverage supports historical reputation, not current staffing or product details.
Use the current privacy policy and product documentation when publishing service-specific claims.

The logo assets were retrieved from:

- `https://haveibeenpwned.com/Images/Hero.svg`
- `https://haveibeenpwned.com/Images/HibpLogo.svg`

These are complete source assets, not reconstructed lockups.
The hero's pale-blue `#C8E5F8` gradient endpoint is documented under `logo.primary`; it is not a general-purpose semantic colour role.

The symbol spread embeds a working loading animation retrieved from the website homepage.
Its five SVG paths and `pulseFade` timing are preserved: a 1.5-second pulse with 0.3-second offsets between bars.
The example adds static reduced-motion and print fallbacks.
Use it to indicate loading or work in progress, alongside a status label, until a result or error is available.
The source stylesheet and animation details are recorded under `logo.animation` in `brand.json`.

The geometry spread uses the unchanged icon paths in an engineering-style SVG diagram.
It highlights the five parallelograms, equal horizontal widths, common lean and aligned sides and baselines.
Construction guides explain the design rather than prescribing a redraw from rounded source coordinates.
The diagram and measured relationships are recorded under `logo.geometry` in `brand.json`.

The three monochrome form examples are unchanged copies of the repository SVGs:
`Logos/Icon/Icon.svg`, `Logos/Icon Pwned/Icon Pwned.svg` and
`Logos/Icon Have I Been Pwned/Icon Have I Been Pwned.svg`.
Keep these local copies in sync if the originals change.

The merchandise review covered all 42 listings in the store's All Products collection,
including sold-out products, and 83 catalogue image views on 13 November 2026.
Not every size or colour variant was individually rendered.
Nine representative images are embedded locally, with product links and treatment guidance.
Their source pages and review scope are recorded under `merchandise` in `brand.json`.
Product mockups are examples of placement and expression, not colour specifications or production masters.

The branded-title spread uses recreated SVG examples inspired by the Merch banner and both titles on the website's Demos page.
All three share a 1200×540 canvas, matching type and icon scale, a continuous blue gradient and the same dark background.
Only the icon and title are shown; secondary logos are omitted to focus on how the visual language extends to other words.
The supplied icon geometry is preserved and Switzer Bold Italic lettering is outlined, with no external font dependency in these SVGs.
These are explanatory illustrations, not original website artwork.
Local image paths and original reference links are recorded under `brandExpressions` in `brand.json`.

## Still to validate

- Numerical logo clear-space and minimum-size rules require visual validation and approval.
  Until then, preserve the artwork, leave it visibly separate from surrounding content and check legibility at the final output size.
- A brand monospace typeface has not been selected; code samples use the system fallback.
- The 8px spacing base is a working guideline, not a measurement of every live layout.
  The 8px, 12px and 16px radius references reflect sampled cards, controls and larger panels.
- Component examples illustrate the visual language, not a complete production or accessibility specification.
  Check contrast, focus, status labels and narrow-screen layouts in context.

## Updating

1. Edit `brand.json` first and retain the distinction between observed usage and proposed standards.
2. Update applicable values in `tokens.css` and `tokens.json`.
3. Update the corresponding copy, examples and styles in `brand-book.html`.
4. Check the rendered spreads for legibility, clipping and consistent artwork.
5. Recheck dated statistics, source links and relationship claims before publication.
