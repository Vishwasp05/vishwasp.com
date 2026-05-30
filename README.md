# vishwasp.com

Built with [Hugo](https://gohugo.io). Deployed on Cloudflare Pages.

## Publishing a new post

**Step 1.** Create a new file in `content/posts/`:

```
content/posts/your-post-slug.md
```

**Step 2.** Start the file with this frontmatter:

```markdown
---
title: "Your Post Title"
date: 2026-06-01
description: "One sentence summary for SEO and social previews."
---

Your content here.
```

**Step 3.** Commit and push:

```bash
git add content/posts/
git commit -m "new post: Your Post Title"
git push
```

Live within ~30 seconds.

## Running locally

```bash
hugo server
```

Open http://localhost:1313
