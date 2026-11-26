---
name: new-post
description: Create a new blog post as a draft page bundle from the archetype. Use when asked to start, draft or write a new post.
---

# New post

## 1. Pick the slug

Lowercase, hyphenated, a few words naming the topic (`frame-allocator`), and
check it is not taken under `content/posts/`. The directory is
`YYYY-MM-<slug>`, with the current year and month.

## 2. Create it

```sh
hugo new content posts/YYYY-MM-<slug>/index.md
```

The `posts` archetype fills the front matter with `draft: true`. Fill in
`title`, `description` and `tags` following the
[writing guide](../../instructions/writing.md).

## 3. Write

Gather the sources first: the engine PR, document or issue the post is about,
and the commit to link. Then follow the writing guide. Images go next to
`index.md` and are referenced by file name.

## Report

The post's path, its sources, and anything left to check with the user.
