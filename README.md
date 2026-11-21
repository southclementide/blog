# Blog

Hugo site (hugo-book theme via Hugo Modules), published to GitHub Pages.

## Content policy

This repo is a git submodule of the private `godfather` notebook monorepo, but
the blog **never reads the notebook directly**. Do not add `module.mounts`,
symlinks, or build steps that point at the parent repo (`../notes`,
`../labs`). Notes can contain private details (hostnames, credentials, internal
topology), so a post is only published after it is deliberately copied into
`content/` and reviewed there.

## Usage

```sh
hugo server        # local preview
hugo --minify      # build into public/ (gitignored)
```

Pushing to `main` deploys to <https://southclementide.github.io/blog/> via
`.github/workflows/pages.yml`.
