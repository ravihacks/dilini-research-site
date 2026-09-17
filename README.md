# Dilini Research Site

A simple professional researcher website with a Markdown blog. Built with [Eleventy](https://www.11ty.dev/) and designed for GitHub + Cloudflare Pages or Netlify.

## Why this setup

- Static HTML output: fast and reliable.
- Markdown blog posts: easy to write and version-control.
- No database or WordPress admin panel.
- Minimal JavaScript.
- GitHub provides history and backup.
- Cloudflare Pages or Netlify can rebuild automatically whenever you push to `main`.

## 1. Install locally

Install Node.js 18 or newer, then from this folder run:

```bash
npm install
npm run start
```

Open `http://localhost:8080`.

For a production build:

```bash
npm run build
```

The finished website is generated in `_site/`.

## 2. Personalise the site

Edit:

```text
src/_data/site.json
```

At minimum, replace:

- `url` with the final domain.
- `email` if you want an email link.
- Google Scholar URL.
- ORCID URL.
- LinkedIn URL.

Replace this image:

```text
src/assets/images/profile-placeholder.svg
```

You can use a JPG, PNG or WebP instead; then update the image path in `src/index.njk`.

### Publications

Edit:

```text
src/publications.md
```

The current publication entries are placeholders on purpose. Replace them with real selected publications.

### Projects

Edit:

```text
src/projects.md
```

## 3. Add a new blog post

Create a new Markdown file inside:

```text
src/blog/posts/
```

Example:

```markdown
---
layout: post.njk
title: A clear post title
date: 2026-09-20
summary: One sentence describing the post.
tags: posts
permalink: /blog/a-clear-post-title/index.html
readingTime: 4 min read
---

Write the article here using Markdown.

## A heading

Normal paragraph text.

- Bullet one
- Bullet two
```

Then run `npm run start` to preview it. The blog index and homepage update automatically.

## 4. Create the GitHub repository

Create an empty GitHub repository, for example:

```text
dilini-research-site
```

Then in this project folder:

```bash
git init
git add .
git commit -m "Initial researcher website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/dilini-research-site.git
git push -u origin main
```

After that, your normal update workflow is:

```bash
git add .
git commit -m "Add new research note"
git push
```

## 5A. Deploy with Cloudflare Pages

In Cloudflare:

1. Open **Workers & Pages**.
2. Create a Pages project and import the GitHub repository.
3. Production branch: `main`.
4. Build command: `npm run build`.
5. Build output directory: `_site`.
6. Save and deploy.

Cloudflare will rebuild the site after new pushes to the connected repository.

### Custom domain

After the first deploy, add the final domain in the Pages project's **Custom domains** area. Then update `site.url` in `src/_data/site.json` to match the real `https://...` address and push the change.

## 5B. Deploy with Netlify

This repo already contains `netlify.toml` with:

```toml
[build]
  command = "npm run build"
  publish = "_site"
```

In Netlify:

1. Add a new project from Git.
2. Select the GitHub repository.
3. Netlify should detect the configuration automatically.
4. Deploy.
5. Add the custom domain under Domain management.

## Recommended workflow

For this website, keep the stack boring:

```text
Write/edit locally
      ↓
Preview with npm run start
      ↓
Commit to Git
      ↓
Push to GitHub
      ↓
Cloudflare Pages OR Netlify automatically builds and deploys
```

Use one host, not both, for the live site. Keeping both deployment files/settings is useful because it makes switching providers easy later.

## Folder structure

```text
.
├── .eleventy.js
├── netlify.toml
├── package.json
├── README.md
└── src
    ├── _data
    │   └── site.json
    ├── _includes
    │   ├── base.njk
    │   └── post.njk
    ├── assets
    │   ├── css/styles.css
    │   ├── images/profile-placeholder.svg
    │   └── js/main.js
    ├── blog
    │   ├── index.njk
    │   └── posts/*.md
    ├── about.md
    ├── contact.md
    ├── index.njk
    ├── projects.md
    ├── publications.md
    └── research.md
```

## Before launch checklist

- Replace profile image.
- Replace the placeholder publication entries.
- Verify biography and role wording.
- Add Scholar / ORCID / LinkedIn URLs.
- Set the real production domain in `site.json`.
- Check every page on mobile and desktop.
- Run `npm run build` before pushing major changes.
- Do not commit private unpublished research data.
