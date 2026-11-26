# AetherEngine Dev Blog

Sources of the [AetherEngine](https://github.com/AIperture-Labs/AetherEngine)
development blog, built with [Hugo](https://gohugo.io) and published on
GitHub Pages at <https://aiperture-labs.github.io/blog/>.

## Write a post

```sh
hugo new content posts/2026-11-my-post/index.md   # a draft page bundle
hugo server -D                      # preview with drafts at http://localhost:1313/blog/
```

Posts are in English. Set `draft: false` when the post is ready; merging
into `main` publishes it.

Supported in posts:

- Code blocks with syntax highlighting (`cpp`, `cmake`, `glsl`, `slang`…).
- Mermaid diagrams: a fenced block with the `mermaid` language.
- Math with KaTeX: `\( inline \)` and `$$ block $$`.

## Layout

The theme is local (`layouts/`, `assets/css/`), with no external theme or
npm dependency. Mermaid and KaTeX are loaded from a CDN, only on pages that
use them.

## Deployment

`.github/workflows/pages.yml` builds the site on every pull request and
deploys it on every push to `main`. In the repository settings, Pages must
use **GitHub Actions** as its source.

## Contributing with an agent

Agents follow [AGENTS.md](AGENTS.md) and the instructions and skills in
`.agents/`.

## License

Posts and pages (`content/`): [CC BY 4.0](LICENSE-CONTENT). Code snippets,
theme, configuration and CI: [MPL-2.0](LICENSE).
