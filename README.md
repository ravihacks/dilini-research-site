# Dilini Research Site

Pure static HTML/CSS/JS professional researcher website for Dr Dilini Perera.

## Architecture

- No WordPress
- No PHP
- No database
- No Eleventy / Node build step
- No Netlify requirement
- GitHub is used only for version history and backup
- Deploy by uploading the repository files to normal web hosting (for example `public_html/`)

## Main structure

```text
.
├── index.html
├── about/
│   └── index.html
├── research/
│   └── index.html
├── publications/
│   └── index.html
├── projects/
│   └── index.html
├── blog/
│   ├── index.html
│   ├── thermal-processing-oat-flour/
│   │   └── index.html
│   └── process-resolved-oat-side-streams/
│       └── index.html
├── contact/
│   └── index.html
└── assets/
    ├── css/styles.css
    ├── js/main.js
    └── images/
```

## How to update a blog post

Each blog article is a normal HTML page inside `blog/<post-slug>/index.html`.

To add a new post:

1. Copy one existing blog post folder.
2. Rename the folder to the new URL slug.
3. Edit the page title, summary, date, image and article content.
4. Add the new post card to `blog/index.html`.
5. Optionally add the newest article to the homepage.
6. Commit the changes to GitHub.
7. Upload the changed files to your hosting.

## Hosting

Upload the repository contents to your domain's web root, commonly:

```text
public_html/
```

The live site can then run directly from your normal hosting account with no build process.

## Before launch

- Replace the profile placeholder with a real professional photo.
- Replace publication placeholders with verified publications.
- Add Google Scholar, ORCID and LinkedIn links.
- Replace the placeholder email/contact details.
- Add the final custom domain to the canonical metadata.
- Keep unpublished or confidential research data out of the repository.
