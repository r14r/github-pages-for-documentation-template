# GitHub Pages documentation template

Reusable Jekyll / Minimal Mistakes documentation website with nested navigation and a sticky scroll-aware TOC.

## Quick start

```sh
just install
just setup
just test
just build
just run
```

Local URL: http://127.0.0.1:4000/github-pages-for-documentation-template/

Public URL: https://r14r.github.io/github-pages-for-documentation-template/

## GitHub Pages deployment (required setting)

In **Settings → Pages → Build and deployment**, select **Source: GitHub Actions** (NOT "Deploy from a branch").

The checked-in `.github/workflows/pages.yml` builds the site using Bundler (which installs the Minimal Mistakes theme), uploads the generated `_site/` files, and deploys via the official GitHub Pages actions. The legacy GitHub Pages automatic Jekyll build cannot resolve the theme gem and must not be used.

The local `just build` command still writes `docs/` for optional static export, but that folder is **not the deployment source** when using the recommended GitHub Actions configuration. Do not commit `docs/` merely to deploy Pages.

## Adapt to another repository

Update `url`, `baseurl`, `project.name` and `project.url` in `_config.yml` to match the destination GitHub Pages URL. Do not include the `docs/` directory name in `baseurl`.

See `just --list` for local commands. `update-cli doctor` validates the Update CLI manifest with your installed version.
