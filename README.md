# Homepage

## Hosting and publishing

This is a Jekyll website hosted at [cshhong.github.io](https://cshhong.github.io/) through GitHub Pages. The GitHub Actions workflow in [`.github/workflows/jekyll.yml`](.github/workflows/jekyll.yml) builds and deploys the site automatically whenever changes are pushed to the `master` branch.

To publish a change, review it locally, then commit and push it to `master`:

```bash
git add .
git commit -m "Describe the change"
git push origin master
```

Deployment progress is available in the repository's **Actions** tab. The live site updates after the deployment workflow completes.

## Where to make edits

- `index.html` — homepage bio, publications/projects, and homepage-specific content.
- `_posts/` — blog posts, written in Markdown with Jekyll front matter.
- `_includes/` — reusable pieces such as the navigation, bibliography, and math setup.
- `_layouts/` — shared blog-page and post-page layouts.
- `css/` — site styling; `css/home.css` controls the homepage.
- `assets/` — images, videos, PDFs, and other files served by the site.
- `_config.yml` — site-wide settings, URL, permalink format, and Jekyll plugins.
- `_bibliography/` — bibliography data and citation style for Jekyll Scholar.

After editing content or adding an asset, run the local server below to confirm links, layout, and rendering before publishing.

## Test locally

Install the Ruby dependencies once (or after changing `Gemfile`):

```bash
bundle install
```

Then start the development server from the repository root:

```bash
bundle exec jekyll serve
```

Open the URL printed in the terminal (normally <http://localhost:4000>). The server watches for most changes; restart it after changing `_config.yml`.

## Template forked from
This repository contains the files needed to replicate my blog: [gregorygundersen.com/blog](http://gregorygundersen.com/blog/).  
For detailed background information, see [this post](http://gregorygundersen.com/blog/2020/06/21/blog-theme).

---

## Changes Made
### Core Updates
- **Gemfile**: Updated to use Jekyll 4.0 and its dependencies.
- **mainjax.html**: Edited to use KaTeX only to prevent conflicts with MathJax.
- **blog.css**: Added `figure-container` class for figures with multiple images.
- **_config.yml**: 
  - Updated `url`.
  - Integrated `ieee.csl` scholar style from Zotero.
- **_includes/bibliography.html**: Added Zotero support to handle double numbering.

### Layout Updates
- **nav.html**: Updated top-bar links.
- **index.html**: Modified homepage links.
- **_layouts/blog_main.html & _layouts/blog_post.html**: Created separate layouts for the blog's main page and individual posts.

### Other Additions
- **.gitignore**: Added `_site` to exclude build files.
- **assets/images**: Created directory to store images used in posts.

---

## Notes
- Jekyll automatically generates the `post.url` value based on the permalink structure defined in `_config.yml` or the front matter of each post.

---

## Useful commands

### Clear Jekyll cache
```bash
rm -rf _site
bundle exec jekyll clean
```
