# Raquel Castillo Bihler — personal website

A simple static one-page site (plain HTML + CSS, no build step).

## Structure

```
index.html          # the homepage
style.css           # styles
images/raquel.jpg   # profile photo
a/                   # a self-contained copy of the site, served at /a/
  index.html
  style.css
  images/raquel.jpg
.github/workflows/deploy.yml   # publishes the site to GitHub Pages on every push
```

All asset paths in the HTML are **relative** (`./style.css`, `./images/raquel.jpg`),
so the site renders identically no matter what URL depth it is served from — the
repo root, a project sub-path (`username.github.io/repo/`), or the `/a/`
sub-folder.

## Publishing on GitHub Pages

1. Create a repository and push these files to the `main` branch.
   - For a site at `https://<username>.github.io/`, name the repo `<username>.github.io`.
   - For a site at `https://<username>.github.io/<repo>/`, name the repo anything.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **GitHub Actions**.

That's it. The included workflow (`.github/workflows/deploy.yml`) runs on every
push to `main` and deploys the site. The live URL appears in Settings → Pages and
in the Actions run summary once it finishes (usually under a minute).

> Prefer no workflow? You can instead pick **Deploy from a branch → `main` → `/ (root)`**
> under the same setting. The `.nojekyll` file in this repo makes that work cleanly too.
> Only use one method at a time.

## The `/a/` page

`https://<your-site>/a/` currently shows the exact same page as the homepage. It
is a standalone copy, so you can later replace everything inside the `a/` folder
(e.g. with a tailored artifact for an application) without touching the main site.
