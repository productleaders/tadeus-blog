# Post file format

One Markdown file per post: `posts/<slug>.md`. UTF-8. The **filename is the URL
slug** — `posts/measuring-ai-adoption.md` → `https://www.tadeus.net/blog/measuring-ai-adoption`.

This is the contract between the publisher (Throughline) and the reader (the
Tadeus site's `src/content.config.ts` `posts` collection). The frontmatter keys
below map 1:1 to that schema.

## Frontmatter (YAML)

| Key | Required | Type | Notes |
| --- | --- | --- | --- |
| `title` | ✅ | string | Post title (H1). |
| `pubDate` | ✅ | date `YYYY-MM-DD` | Publish date. Drives ordering + `datePublished`. |
| `updatedDate` | — | date | If present → `dateModified`. |
| `description` | — | string | Excerpt for the listing card + meta description fallback. |
| `metaTitle` | — | string (≤60) | SEO `<title>` override. |
| `metaDescription` | — | string (≤155) | SEO meta description override. |
| `heroImage` | — | string | Repo-relative path to an image file, e.g. `images/<slug>.png`. (An absolute URL or an inline base64 data URI also work.) |
| `heroImageAlt` | — | string | Alt text for the hero (accessibility + SEO). |
| `author` | — | string | Display name. |
| `tags` | — | string[] | First tag shown as the card eyebrow + post kicker. |
| `faqs` | — | `{question, answer}[]` | Rendered as `FAQPage` JSON-LD (answer-engine optimization). |
| `draft` | — | boolean | `true` = built in dev only, never published live. |

## Body

GitHub-Flavored Markdown after the frontmatter. Links are normal Markdown links.
Reference images by their repo-relative path, e.g. `![alt](images/<slug>.png)`.

## Images = files under `images/`

Each image is a normal file committed to `images/` (the publisher uploads it via
the GitHub API, which base64-encodes the bytes on the wire). Posts reference it
**repo-relative** as `images/<name>`, so the repo stays self-consistent and the
image renders in GitHub's own preview. At build the site copies `images/` into
`/blog-images/` (cached forever) and rewrites `images/…` → `/blog-images/…`.

> Inline base64 data URIs (`![](data:image/png;base64,…)`) are still accepted and
> decoded to files — a fallback — but separate files are preferred (GitHub caps
> single-file commits near 1 MB, and they keep diffs clean).

## Minimal example

```markdown
---
title: "Measuring AI adoption beyond seat activity"
pubDate: 2026-07-01
description: "Seat counts tell you who logged in, not who changed how they work."
metaTitle: "How to measure AI adoption (not just seats)"
metaDescription: "A practical guide to measuring real AI adoption — usage, blockers, and behaviour change — not login telemetry."
heroImage: "images/measuring-ai-adoption.png"
heroImageAlt: "Tadeus — measuring AI adoption"
author: "Tadeus Team"
tags: ["AI adoption"]
faqs:
  - question: "What is AI adoption measurement?"
    answer: "Measuring whether people changed how they work with a tool — not just whether they logged in."
draft: false
---

## The seat-activity trap

Most teams measure adoption by counting active seats…
```
