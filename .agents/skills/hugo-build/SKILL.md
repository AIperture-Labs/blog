---
name: hugo-build
description: Build the blog with Hugo the way CI does, failing on any warning. Use after editing a post, a page, the theme or hugo.toml, and before committing.
---

# Build

Needs Hugo extended, at the version pinned by `HUGO_VERSION` in
`.github/workflows/pages.yml`. Check with `hugo version`.

## 1. Build

Published posts only, as CI does:

```sh
hugo --gc --minify --panicOnWarning
```

Including drafts, to check a post in progress:

```sh
hugo --gc --minify --panicOnWarning --buildDrafts
```

Output goes to `public/`, ignored by git. Never commit it.

## 2. Check

- The build ends without warning or error.
- Every relative link of the changed posts resolves: open the generated page,
  or search `public/` for the link target.

## Report

The build result, and the warnings or errors with the file they point to.
