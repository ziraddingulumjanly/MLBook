# Jupyter Book setup for this repo

This repository has been prepared to build a static Jupyter Book website from the existing notebook portfolio.

## Local build

From the repository root, run:

```bash
pip install -r requirements.txt
jupyter-book build .
```

Then open:

```text
_build/html/index.html
```

## GitHub Pages deployment

1. Push the repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **GitHub Actions** as the source.
4. Go to the **Actions** tab and check the `deploy-book` workflow.

When it succeeds, the website should be available at a URL like:

```text
https://ziraddingulumjanly.github.io/ML-projects/
```

## Adding new notebooks

1. Put the notebook in the correct folder.
2. Add its path to `_toc.yml` without the `.ipynb` extension.
3. Run `jupyter-book build .` locally.
4. Commit and push.

## Important note

The book uses:

```yaml
execute:
  execute_notebooks: "off"
```

This means the notebooks are not rerun during build. The website displays saved notebook outputs. This is safer for projects that depend on local data files, Snowflake credentials, `.env` files, or long-running ML workflows.
