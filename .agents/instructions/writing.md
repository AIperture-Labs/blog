# Writing guide

## Posts

A post explains one design decision or one piece of the engine in depth: the
problem, the options, the choice and why, then the code. It should be useful on
its own to someone building an engine, without having read the others.

- Start from something real in the engine: a merged PR, a document in `docs/`,
  an issue. Link it.
- Lead with the problem, not with the history of the work.
- Give the reasons and the trade-offs, including the options not taken.
- End with what is still open or comes next, in a short section.
- Write in the first person singular for the author's choices; avoid "we"
  unless several people did the work.

## Engine facts and code

- Every claim about the engine is checked against its repository. Link to the
  code with a permalink on a commit (`/blob/<sha>/…`), not on a branch, so the
  post keeps pointing at what it describes.
- Snippets are copied from the engine, then trimmed (`// …` marks a cut);
  never write code the engine doesn't have and present it as the engine's.
  Pseudo-code is labeled as such.
- Name engine types, functions and modules exactly as the code does, in
  inline code.

## Front matter

```yaml
title: "Short title, sentence case"
date: YYYY-MM-DD
description: "One or two sentences for the index, the feed and search engines."
tags: [architecture, cpp]
draft: true
```

Tags are lowercase, from those already used (`/tags`) when one fits.

## Markdown

- Lines wrap at 80 columns, except front matter, tables, links and code blocks.
- No `#` title in the body: the front matter's `title` is the title. Sections
  are `##`, then `###`.
- Code blocks name their language (`cpp`, `cmake`, `slang`, `sh`…).
- Diagrams are Mermaid code blocks, or SVG files in the post bundle. Math uses
  `\( … \)` inline and `$$ … $$` for blocks.
- Images have an alt text that says what they show.
