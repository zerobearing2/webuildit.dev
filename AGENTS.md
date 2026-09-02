# webuildit.dev

Static GitHub Pages front door for `webuildit.dev`. Campfire runs on a VPS at `chat.webuildit.dev` and is outside this repo.

## Always

- Edit `public/`. That directory is the Pages artifact. No build step.
- Default branch is `master`.
- Local server: `npx serve public -l 4000`.
- After changing CSS, JS, or images, restamp every `?v=` in `public/index.html` and `public/404.html` (including Open Graph, Twitter, and JSON-LD URLs) to a content hash of the new file. Commit the asset and those references together. Done when every changed file's hash matches every HTML reference.
- QA with `agent-browser` against the local server. Exercise the changed path, then desktop and a ~390px viewport.
- Chat links use the label `Open the room`.
- Type is self-hosted in `public/fonts/` and loaded with `@font-face` in `public/style.css`.

## Hosting

`.github/workflows/github-pages.yml` uploads `public/` on push to `master`. `public/CNAME` is `webuildit.dev`.

Keep `chat.webuildit.dev` as A records to the Campfire VPS (Cloudflare proxied, Full strict). That name is not a GitHub Pages host.
