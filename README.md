# Dilini Research Site

Pure static HTML/CSS/JS professional researcher website for Dr Dilini Perera.

## Architecture
- No WordPress, PHP or database
- No build step
- No Netlify requirement
- GitHub is used only for version history and backup
- Upload the files directly to your hosting web root, usually `public_html/`

## Blog workflow
1. Add/edit an article HTML page under `blog/<slug>/index.html`.
2. Add/update its metadata in `assets/js/blog-data.js`.
3. The homepage and blog listing update automatically from that data.
4. Commit and push to GitHub.
5. Upload changed files to your hosting.

## Before launch
- Replace the profile placeholder with a professional photo.
- Replace publication placeholders with verified publications.
- Add Google Scholar, ORCID and LinkedIn links.
- Add the final domain to canonical metadata if desired.
- Keep confidential/unpublished research data out of the repository.
