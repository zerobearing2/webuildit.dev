# webuildit.dev

Static front door for [webuildit.dev](https://webuildit.dev). The chat lives at [chat.webuildit.dev](https://chat.webuildit.dev).

## Local

```bash
npx serve public -l 4000
```

Then open http://localhost:4000.

The deployable site is self-contained in `public/`. No build step.

## GitHub Pages

Push to `master` or run `.github/workflows/github-pages.yml` by hand. The workflow uploads `public/` only. `public/CNAME` is `webuildit.dev`.

## License

MIT. See [LICENSE](LICENSE).
