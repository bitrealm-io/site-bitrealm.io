# bitrealm.io

The one-page site for Bitrealm LLC. Plain HTML and CSS, no build step, no JavaScript, no forms.

## Files

- `index.html` – the page
- `404.html` – not-found page; Cloudflare Pages serves it with a real 404 status
- `style.css` – the styles (dark theme, IBM Plex Mono)
- `fonts/` – IBM Plex Mono, self-hosted so the page loads nothing from third parties
- `favicon.svg`, `favicon.ico`, `apple-touch-icon.png` – the bracket mark as tab and home-screen icons
- `og.png` – 1200×630 preview image for shared links
- `_headers` – security headers Cloudflare Pages applies to every response
- `robots.txt`, `sitemap.xml`
- `brand/` – the brand style guide: `Bitrealm-LLC-Brand-Style-Guide.pdf` and its source, `brand-style-guide.html`. Rebuild the PDF from inside `brand/` with `chromium --headless --no-pdf-header-footer --print-to-pdf=Bitrealm-LLC-Brand-Style-Guide.pdf brand-style-guide.html`

## Deploy on Cloudflare Pages

1. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
2. Pick `bitrealm-io/site-bitrealm.io`, production branch `main`.
3. Build settings: framework preset **None**, build command **empty**, build output directory **/** (the repo root).
4. Save and deploy. You get a `*.pages.dev` URL immediately.
5. In the project, **Custom domains** → **Set up a custom domain** → `bitrealm.io`. Cloudflare adds the DNS record for you when the zone is already on Cloudflare; add `www.bitrealm.io` the same way if you want it.

Every push to `main` redeploys. Other branches get preview URLs.

## Edit

Serve the folder locally to preview (`python3 -m http.server`), since the page uses root-relative paths. There is nothing to install.
