# GitHub Pages documentation template

Reusable Jekyll / Minimal Mistakes documentation website with three-column layout, nested navigation and scroll-aware sticky TOC.

## Quick start

Install Ruby, Bundler and `just`.

```sh
just install
just setup
just test
just build
just run
```

Local preview (as configured for the example destination):
http://127.0.0.1:4000/unified-office-workshop-public/

## GitHub Pages: branch-based publication

This template is configured for **Settings → Pages → Deploy from a branch → main /docs**.

Source stays at repository root. `just build` writes the generated static website to `docs/` and creates `docs/.nojekyll` so Pages does not attempt to run another Jekyll build.

A GitHub Actions workflow checks the project and commits regenerated `docs/` contents to `main` after pushes. GitHub Pages serves the committed `docs/` directory; the folder name is **not** part of the public URL. On protected branches, direct workflow pushes may be rejected; configure an appropriately authorized deployment process instead.

## Project URLs

For https://r14r.github.io/unified-office-workshop-public/ use:

```yaml
url: "https://r14r.github.io"
baseurl: "/unified-office-workshop-public"
project:
  url: "https://r14r.github.io/unified-office-workshop-public/"
```

When copying this template to a different repository, replace `unified-office-workshop-public` in `_config.yml` with the destination repository name. The `docs/` build location does not change the `baseurl`.

## Notes

- `just test` builds a temporary verification site under `_site/`.
- `just build` generates `docs/` for publication.
- `just run` serves locally using the configured `baseurl`.
- `just clean` deletes the generated `docs/` and `_site/` directories; do not put authored source files under `docs/`.
- Run `update-cli doctor` and `update-cli setup --list` to validate your installed Update CLI version.
