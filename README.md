# GitHub Pages documentation template

Reusable Jekyll / Minimal Mistakes documentation website with hierarchical navigation and sticky scroll-aware right TOC.

## Install and develop

Install Ruby, Bundler and `just`.

```sh
just install
just setup
just test
just build
just run
```

Local URL in the included example:
http://127.0.0.1:4000/github-pages-for-documentation-template/

## GitHub Pages: Deploy from a branch, main /docs

Place the **Jekyll source at repository root**. Configure Settings → Pages → **Deploy from a branch**, branch `main`, folder `/docs`.

`just build` generates static files under `docs/` with `docs/.nojekyll`. To publish them, commit and push those generated files:

```sh
just build
git add -A docs
git commit -m "docs: publish generated site"
git push origin main
```

A GitHub Actions workflow **validates** the build, but intentionally does not push generated files. Commits written with its normal `GITHUB_TOKEN` do not trigger a new Pages build. Generate and commit from a normal developer account, or use a separately authorized publishing workflow.

The folder `docs/` controls where Pages reads files; it is **not part of the final URL**.

## Destination URL configuration

For https://r14r.github.io/github-pages-for-documentation-template/:

```yaml
url: "https://r14r.github.io"
baseurl: "/github-pages-for-documentation-template"
project:
  url: "https://r14r.github.io/github-pages-for-documentation-template/"
```

Change `baseurl` and `project.url` for each repository built from this template. The template's example is not automatically derived from the repository name.

`just test` uses `_site/`; `just build` uses `docs/`; `just run` serves locally using the configured baseurl. `just clean` deletes generated output, including `docs/`; do not put source content under `docs/`.

Update CLI compatibility can be checked with `update-cli doctor` and `update-cli setup --list`.

## Publishing branch-based Pages

With Settings → Pages configured to **main /docs**, the generated site must be committed:

```sh
just build
git add -f docs/.nojekyll
git add -A docs/
git commit -m "docs: publish generated static website"
git push origin main
```

The generated `docs/index.html` must exist on GitHub. The `docs` folder is not part of the public URL. The included Actions workflow validates the build but does not commit `docs/` for you.
