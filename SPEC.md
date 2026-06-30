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
| `heroImage` | — | string | **Base64 data URI** (`data:image/png;base64,…`) or a `/blog-images/…` path or an absolute URL. The site decodes base64 to a cacheable file at build. |
| `heroImageAlt` | — | string | Alt text for the hero (accessibility + SEO). |
| `author` | — | string | Display name. |
| `tags` | — | string[] | First tag shown as the card eyebrow + post kicker. |
| `faqs` | — | `{question, answer}[]` | Rendered as `FAQPage` JSON-LD (answer-engine optimization). |
| `draft` | — | boolean | `true` = built in dev only, never published live. |

## Body

GitHub-Flavored Markdown after the frontmatter. Links are normal Markdown links.
Inline images may also be base64 data URIs (`![alt](data:image/...;base64,...)`);
the site decodes those to files too.

## Images = base64 (self-contained)

Images travel **inside the post file** as base64 so a post is one portable file
and the repo stays text-only (no binary blobs). At build the site extracts every
data URI, writes it to `/blog-images/<sha256>.<ext>` (cached forever, hash-named),
and rewrites the reference — so the **served** pages stay lean and fast.

## Minimal example

```markdown
---
title: "Measuring AI adoption beyond seat activity"
pubDate: 2026-07-01
description: "Seat counts tell you who logged in, not who changed how they work."
metaTitle: "How to measure AI adoption (not just seats)"
metaDescription: "A practical guide to measuring real AI adoption — usage, blockers, and behaviour change — not login telemetry."
heroImage: "data:image/png;base64,iVBORw0KGgo…"
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
