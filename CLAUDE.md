# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for **EndoLaser**, a laser hair removal and aesthetic treatments clinic in São Paulo, Brazil. Deployed to GitHub Pages. The site targets women aged 25-55, focused on converting visitors to WhatsApp sales.

Live URL: `https://matheus-maia.github.io/page-clinica-estetica/`

## Development

No build step or package manager. To preview locally:

```bash
python -m http.server 8000
# or
npx http-server
```

Open `http://localhost:8000` in the browser.

## Tech Stack

- **HTML5** — single file (`index.html`) contains the entire site
- **Tailwind CSS** — served via local `/css/tailwind.min.css`; custom theme colors are configured inline in `index.html` using the Tailwind v4 `@theme` block
- **Font Awesome 6.4.0** — icon library via CDN
- **Vanilla JS** — inline at bottom of `index.html`

## Architecture

Everything lives in `index.html` (~844 lines). Sections in order:

1. Header / sticky nav with mobile hamburger menu
2. Hero — background image + CTA buttons
3. Benefits — 3-column grid
4. How treatment works — text + image
5. Treatment areas — 5-column grid (face, underarms, arms, abdomen, legs)
6. Before/after results
7. Testimonials
8. About the clinic
9. CTA for scheduling
10. FAQ accordion
11. Contact form (no backend)
12. Embedded Google Maps
13. Footer
14. Floating WhatsApp button (fixed position)

JavaScript (bottom of `index.html`) handles: mobile menu toggle, FAQ accordion (one open at a time), smooth scrolling with header offset, mobile menu auto-close on navigation.

## Custom Tailwind Theme Colors

Defined in the `<style>` block inside `index.html`:

| Token | Hex | Usage |
|-------|-----|-------|
| `primary` | `#8B5FBF` | Purple — main brand color |
| `secondary` | `#FF6B6B` | Red/coral — accents and CTAs |
| `dark` | `#2D3748` | Dark text |
| `light` | `F7FAFC` | Light backgrounds |

## Media Files

Images are referenced under `/midia/` — this directory must be populated with actual image files. Check the HTML for `src="/midia/..."` attributes to see what's expected.

## SEO

The site has thorough SEO optimization. See [docs/optimizações-de-seo.md](docs/optimizações-de-seo.md) for the full guide. Key elements already implemented: meta description, Open Graph / Twitter Cards, Schema.org JSON-LD (`LocalBusiness`), canonical link, sitemap, and robots.txt.

## Language

All content is in Brazilian Portuguese (pt-BR). Keep all user-facing text, commits, and documentation in Portuguese unless the existing pattern differs.
