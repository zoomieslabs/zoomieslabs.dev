# zoomieslabs.dev

The ZoomiesLabs website. Plain static HTML and CSS: no framework, no build step, no JavaScript, no cookies, no trackers, and no requests to third-party domains.

- `index.html`: the studio home
- `retramo.html`: the Retramo page, served at `/retramo`
- `404.html`: not-found page
- `assets/site.css`: the one stylesheet, with the brand tokens
- `assets/brand/`: logos and icons (the `-tight` files crop the same artwork to the drawing, for lockups)
- `assets/fonts/`: Bricolage Grotesque, Atkinson Hyperlegible Next and Mono (latin subsets from Google Fonts, SIL Open Font License, licenses alongside)
- `_headers`: security and cache headers, read by Cloudflare Pages

## Deploy

Cloudflare Pages project `zoomieslabs`, connected to this repository: framework preset **None**, build command empty, build output directory **/**. Every push to `main` deploys to production; other branches get preview URLs.

Custom domains: `zoomieslabs.dev` and `www.zoomieslabs.dev`. The www → apex 301 lives in a Cloudflare Redirect Rule on the zone ("Redirect www to zoomieslabs.dev"), because Pages' `_redirects` file doesn't accept absolute URLs as a source.

## Preview locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. (`/retramo` needs Cloudflare's clean URLs; locally, open `/retramo.html`.)
