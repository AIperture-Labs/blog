# Repository layout

Where things live. Read this before creating a file or a directory; if nothing
fits, ask instead of adding a top-level directory.

| Path                                 | Content                                                  |
| ------------------------------------ | -------------------------------------------------------- |
| `content/posts/YYYY-MM-<slug>/`      | One post as a page bundle: `index.md` and its images     |
| `content/<page>/index.md`            | Standalone pages (`about`)                               |
| `archetypes/`                        | Front matter templates for `hugo new`                    |
| `layouts/`                           | The theme's Hugo templates and render hooks              |
| `assets/css/`                        | The theme's styles (`main.css`) and code highlighting    |
| `.github/workflows/`                 | CI: build on pull requests, deploy to Pages from `main`  |
| `.agents/`                           | AI agent instructions (`instructions/`) and `skills/`    |
| `.claude/skills`                     | Symlink to `.agents/skills`                              |
| `.worktrees/`                        | Git worktrees, ignored by git                            |

Root files: `README.md`, `AGENTS.md`, `LICENSE`,
`LICENSE-CONTENT`, `hugo.toml`, `.editorconfig`,
`.gitattributes`, `.gitignore`. `public/` and `resources/_gen/` are build
outputs, ignored by git.

## Naming

- File and directory names are lowercase, words separated by hyphens.
- A post's directory starts with its year and month, then a short slug:
  `2026-11-starting-over`. The slug is the post's URL; never rename a
  published one.
- Images in a post bundle are named after what they show
  (`module-graph.svg`), not numbered.

A new directory or a new kind of file updates this page in the same change.
