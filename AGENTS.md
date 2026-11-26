# AI Agents Instructions

Adapted from the
[AetherEngine](https://github.com/AIperture-Labs/AetherEngine/blob/dev/AGENTS.md)
instructions, for a blog about the engine instead of the engine's code.

## The Eleven Commandments

For every agent, on every task:

1. Thou shalt state thy assumptions, and ask when unsure.
2. Thou shalt present every interpretation of a request, and never pick one
   silently.
3. Thou shalt propose the simpler solution when one exists, even against the
   user's idea.
4. Thou shalt stop and ask when something is unclear, saying exactly what.
5. Thou shalt do only what is asked: no extra post, section, page or theme
   feature.
6. Thou shalt not invent: every fact about the engine comes from its code, its
   docs or its history, and every quote from its source; when unsure, say so
   or leave it out.
7. Thou shalt be concise and compact, without repetition, and cut in a post
   what does not teach something.
8. Thou shalt show the real code: snippets match the engine at the linked
   commit, and are trimmed, never rewritten.
9. Thou shalt follow the writing rules strictly. Where none exists, thou shalt
   neither invent one nor mix styles, but ask, and the rule gets added to
   `.agents/`.
10. Thou shalt not touch posts next to the change, nor rewrite published text,
    unless that is the request.
11. Thou shalt stay agnostic: nothing specific to a person or a machine (name,
    email, path, host) is hardcoded, outside the header comments; site-wide
    values live in `hugo.toml`.

## Security

Never write a login, password, token, key or any other secret in posts,
configs, commits, PRs or issues. If a secret leaks, stop and tell the user: it
must be rotated, deleting the commit is not enough.

## Language

English is the language of the repo: posts, pages, theme, docs, commits and
PRs. Interactive exchanges with the user use the user's language.

## Repository Workflow

Branches, commits, pull requests and publishing: read
[repo-workflow.md](.agents/instructions/repo-workflow.md) before any git,
branch, commit, PR or issue operation.

## Repository Layout

Where files live: read [repo-layout.md](.agents/instructions/repo-layout.md)
before creating a file or a directory.

## Writing Workflow

Writing or editing a post follows the same loop; a post is ready only when one
pass goes through clean:

1. Read the [writing guide](.agents/instructions/writing.md).
2. Create the post with the [new-post](.agents/skills/new-post/SKILL.md)
   skill, or edit the existing one.
3. Check every engine fact and snippet against the engine repository, at the
   commit the post links to.
4. Build with the [hugo-build](.agents/skills/hugo-build/SKILL.md) skill: no
   warning, no broken link.
5. If any step fails, fix and restart from step 3; otherwise, hand the post
   over for review with the [hugo-preview](.agents/skills/hugo-preview/SKILL.md)
   skill.

A post stays `draft: true` until the user says it is ready.

## Theme

The theme is local (`layouts/`, `assets/css/`) and follows the AIperture Labs
identity of the organization profile (`scripts/roadmap.py` in
`AIperture-Labs/.github`): its colors live as variables at the top of
`assets/css/main.css`. Change them there, never inline, and keep the theme free
of npm and external themes.

## Header Comment

Every source or config file starts with a header comment (copyright, license
and, if useful, documentation), in the file's comment syntax: `{{/* */}}` in
Hugo templates, `/* */` in CSS, `#` in TOML and YAML.

- `Copyright (c) <year> AIperture-Labs <xavier.beheydt@gmail.com>` then
  `SPDX-License-Identifier: MPL-2.0`.
- Then, if useful, a `Doc:` line linking the documentation of the format or
  the tool the file configures.
- `<year>` is the current year.

Posts, pages and other Markdown files have none: their text is under
CC BY 4.0 ([LICENSE-CONTENT](LICENSE-CONTENT)), the code under MPL-2.0
([LICENSE](LICENSE)).

## Skills

Procedures live in `.agents/skills/<name>/SKILL.md`; use the matching one
instead of improvising the command:

- [new-post](.agents/skills/new-post/SKILL.md): create a post as a draft page
  bundle.
- [hugo-build](.agents/skills/hugo-build/SKILL.md): build the site as CI does,
  failing on any warning.
- [hugo-preview](.agents/skills/hugo-preview/SKILL.md): serve the site with
  drafts, for review.

## New tool or feature

Introducing a new tool or feature (a shortcode, a CI step, a dependency) adds
its skill (`.agents/skills/<tool>-<action>`) when it has a procedure, updates
[repo-layout.md](.agents/instructions/repo-layout.md) if it changes where files
live, and is listed in [Skills](#skills) in the same change.
