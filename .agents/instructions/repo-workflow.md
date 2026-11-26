# Repository workflow

Branches, commits, pull requests and publishing. Read this before any git,
branch, commit, PR or issue operation.

## Branches

- `main` — the only permanent branch, and what is published. Never commit
  directly on it.
- One branch per change, created from `main`, named `<type>/<short-description>`
  where `<type>` is a Conventional Commits type: `docs/` for a post or a page
  (e.g. `docs/starting-over`), `feat/` or `fix/` for the theme, `ci/`,
  `chore/`.
- Never delete a branch, locally or on the remote, without asking the user
  first.

Work in a worktree under `.worktrees/`, ignored by git, named after its branch:

```sh
git worktree add -b docs/my-post .worktrees/docs/my-post main
```

## Commits

- Follow Conventional Commits: <https://www.conventionalcommits.org/en/v1.0.0/>.
  Format: `type(scope): description`. The scope is the area touched: `posts`,
  `pages`, `theme`, `ci`, `agents` or `readme`.
- Keep commits small and atomic: one post, or one coherent change.
- Commit a step only after the user has reviewed it.
- An agent may co-sign its commits and PRs with its own name and the model used,
  as a `Co-Authored-By:` trailer. If the user opposes it, don't.

## Pull requests

- Branch → `main`, merged with a squash merge. The PR title follows Conventional
  Commits: the squash keeps it as the commit message.
- CI builds every pull request; a red build is never merged.

## Publishing

Every push to `main` deploys the site to GitHub Pages
(`.github/workflows/pages.yml`). Merging a post with `draft: false` publishes
it: only the user decides when, by flipping the flag or asking for it.

## Tracking

Post ideas and theme work are tracked with GitHub issues, not with to-do files
in the repository. An issue for a post names the engine change, PR or document
it is about.
