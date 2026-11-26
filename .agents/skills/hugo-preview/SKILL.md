---
name: hugo-preview
description: Serve the blog locally with drafts and live reload so the user can review a post or a theme change. Use when asked to preview, show or review the site.
---

# Preview

```sh
hugo server --buildDrafts --navigateToChanged
```

The site is served at the address Hugo prints (by default
`http://localhost:1313/blog/`, the path coming from `baseURL` in `hugo.toml`)
and reloads on every save. Stop it with `Ctrl+C` when the review is over.

When the user cannot open a local server, build with the
[hugo-build](../hugo-build/SKILL.md) skill and share screenshots of the changed
pages instead.

## Report

The URL of each changed page.
