# freerisestudio.com

The "coming soon" splash site for **FreeRise Studio**.

Plain static HTML/CSS with no build step: everything in this folder is served as is.

| File | What it is |
| --- | --- |
| `index.html` | The page. The animated splash (paper mountains, gold rays, feather + wordmark) is inline SVG with CSS animation. |
| `favicon.svg`, `favicon.ico`, `apple-touch-icon.png`, `icon-*.png`, `site.webmanifest` | Feather icons for browser tabs, phones and bookmarks. |
| `og-image.png` | Preview image shown when the link is shared on X, Discord, etc. |
| `fonts/bricolage-700.woff2` | Bricolage Grotesque Bold (SIL Open Font License), subset to Latin. |
| `_headers` | Cloudflare Pages response headers (security headers, font caching). |

## Deploying on Cloudflare Pages

Workers & Pages → Create → Pages → Connect to Git → pick this repo, then:

- Production branch: `main`
- Framework preset: `None`
- Build command: *(leave empty)*
- Build output directory: `/`

Every merge to `main` deploys automatically. Then add `freerisestudio.com` (and `www`) under the project's **Custom domains** tab.

## Editing

- Social links and the contact email are near the bottom of `index.html`.
- When the Discord invite exists, replace the `<span class="soon" …>` item with a link like the others.
