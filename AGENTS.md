# webuildit.dev

Static GitHub Pages front door for `webuildit.dev`. The chat itself is a Discord server at `https://discord.gg/ExQHdWPSp` and is outside this repo.

## Always

- Edit `public/`. That directory is the Pages artifact. No build step.
- Default branch is `master`.
- Local server: `npx serve public -l 4000`.
- After changing CSS, JS, or images, restamp every `?v=` in `public/index.html` and `public/404.html` (including Open Graph, Twitter, and JSON-LD URLs) to a content hash of the new file. Commit the asset and those references together. Done when every changed file's hash matches every HTML reference.
- QA with `agent-browser` against the local server. Exercise the changed path, then desktop and a ~390px viewport.
- Chat links use the label `Open the room` and point at the Discord invite. There is one invite URL; if it changes, update both links in `public/index.html` plus the four meta/JSON-LD descriptions.
- Type is self-hosted in `public/fonts/` and loaded with `@font-face` in `public/style.css`.

## Hosting

`.github/workflows/github-pages.yml` uploads `public/` on push to `master`. `public/CNAME` is `webuildit.dev`.

Nothing on the site points at `chat.webuildit.dev` any more — the room moved to Discord. The old Campfire A records and VPS are still live and now unreferenced; tear them down or redirect the hostname when you're ready.
