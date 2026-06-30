# tadeus-blog

Blog content for **[tadeus.net/blog](https://www.tadeus.net/blog)**.

Each post is a Markdown file under `posts/`, carrying its own SEO/AEO metadata,
with images committed as files under `images/`.
[Throughline](https://www.tadeus.net) writes these (its GitHub publisher); the
Tadeus site container polls this repo (~every 10 min), copies the images into its
served assets, rebuilds, and serves the result. No CMS, no database.

- **Format contract:** [`SPEC.md`](SPEC.md) — the exact file shape. Do not change
  it without updating the site's `src/content.config.ts` (the reader) in lockstep.
- **Posts:** `posts/<slug>.md` — the filename is the URL slug
  (`/blog/<slug>`). Keep slugs stable (they're tracked in Search Console).
- **Cadence:** a couple of posts a day at most.

This repo is intentionally **public** — it's blog copy, and a public repo means the
site can pull it with no credentials.
