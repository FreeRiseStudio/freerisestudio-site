# freerisestudio.com

The "coming soon" splash site for **FreeRise Studio**.

Plain static HTML/CSS with no build step: everything in `public/` is served as is.

| File (in `public/`) | What it is |
| --- | --- |
| `index.html` | The page. The animated splash (paper mountains, gold rays, feather + wordmark) is inline SVG with CSS animation. |
| `favicon.svg`, `favicon.ico`, `apple-touch-icon.png`, `icon-*.png`, `site.webmanifest` | Feather icons for browser tabs, phones and bookmarks. |
| `og-image.png` | Preview image shown when the link is shared on X, Discord, etc. |
| `fonts/bricolage-700.woff2` | Bricolage Grotesque Bold (SIL Open Font License), subset to Latin. |
| `_headers` | Response headers (security headers, font caching). |

## Deploying on Cloudflare (Workers)

`wrangler.jsonc` tells Cloudflare to serve the `public/` folder as static assets.
The Worker is connected to this repo, with:

- Production branch: `main`
- Build command: *(empty)*
- Deploy command: `npx wrangler deploy`

Every merge to `main` deploys automatically. Add `freerisestudio.com` (and `www`) under the Worker's
**Settings → Domains & Routes**. The `name` in `wrangler.jsonc` must match the Worker's name in the dashboard.

## Editing

- Social links and the contact email are near the bottom of `public/index.html`.
- When the Discord invite exists, replace the `<span class="soon" …>` item with a link like the others.
