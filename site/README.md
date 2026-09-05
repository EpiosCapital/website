# Epios Capital — static site

Plain HTML/CSS. No build step, no JavaScript, no dependencies other than the
Google Fonts stylesheet (Archivo + JetBrains Mono).

## Files

- `index.html` — the whole site
- `favicon.svg`
- `robots.txt`

## Hosting

Upload the contents of this folder to any static host:

- **Netlify / Vercel / Cloudflare Pages** — drag the folder in, or point at the repo with no build command and this folder as the output directory.
- **GitHub Pages** — commit the contents to the repo root (or `/docs`) and enable Pages.
- **S3 / nginx / Apache** — copy the files into the web root; set `index.html` as the index document.

Local preview: open `index.html` directly, or run `python3 -m http.server` in this folder.

## Updating the monthly numbers

All figures currently render as `—` (site marked under development). To publish real data,
search `index.html` for `—` and replace within these blocks:

- hero stat grid (`AUM`, `MoM`, `STRATEGIES`, `UPDATED`)
- `#transparency` table rows and the four summary cells
- `#instruments` eyebrow period and the three `card-detail` lines
- footer `UPDATED —`
- the two ticker spans at the top (keep both copies identical — the duplicate makes the scroll loop seamless)

Remove the `.devbanner` block and the "SITE UNDER DEVELOPMENT" ticker text when the site goes live.

## Offline fonts

To drop the Google Fonts dependency, download the two families, place the `.woff2` files
in `fonts/`, and replace the `<link>` tags in `<head>` with `@font-face` rules.
