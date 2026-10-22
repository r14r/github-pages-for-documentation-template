# GitHub Pages documentation template

Reusable Jekyll / Minimal Mistakes documentation website.

Features: hierarchical left navigation with red active-page border, sticky right-side table of contents, automatic ScrollSpy highlighting, Jekyll Markdown pages, GitHub Pages deployment, Just recipes, Update CLI manifest.

## Quick start

Install Ruby, Bundler and `just`. Then:

```sh
just install
just setup
just test
just build
just run
```

Site: http://127.0.0.1:4000/github-pages-for-documentation-template/

## Customize for another repository

Update `url`, `baseurl`, `title` in `_config.yml`; edit `_data/navigation.yml`; replace sample Markdown pages.

## Update CLI

Use `update-cli doctor` and `update-cli setup --list` to validate against your installed Update CLI version. The bundled manifest follows schemaVersion 2.

## Versioning

`VERSION` starts at 0.0.1 (first committed template release). Bump SemVer in each future change before merging. Automatic GitHub commit/merge bumping is not implemented.
