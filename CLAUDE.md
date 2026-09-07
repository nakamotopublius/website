# publiusnakamoto.com

Static HTML site for Publius Nakamoto's course-study project (Peterson Academy write-ups: overview videos, slide decks, podcasts, study guides).

## Structure
- `index.html`, `about.html`, `contact.html`, `projects.html` — plain HTML pages, no templating.
- `assets/style.css` — a **pre-compiled** Tailwind utility stylesheet checked directly into the repo. There is no build step, no `package.json`, no Tailwind config in this repo.
  - Utility classes already present in this file work immediately in HTML (e.g. `text-blue-600` was already generated and available).
  - A utility class that *isn't* already in `style.css` will not do anything — it has to be added as raw CSS by hand, or the file regenerated elsewhere with a Tailwind build and re-copied in. Don't assume any Tailwind class works without checking `assets/style.css` first (`grep` for it).
- `assets/portrait-sketch.webp` — portrait image used on the home page.

## Deploy
- GitHub repo: https://github.com/nakamotopublius/website (public).
- Netlify auto-deploys the live site from the `main` branch on every push — no manual deploy step. Check https://publiusnakamoto.com/ after pushing to confirm it rebuilt.
- The repo was made public specifically to resolve a Netlify "unrecognized Git contributor" build block — see `claude-setup-check.md` for that history.

## Workflow notes
- Preview changes locally before pushing: `python3 -m http.server 8934 --directory .` and open `http://localhost:8934/`.
- This is a small enough site that direct edits + push to `main` is the normal workflow — no PR/branch process currently in use.
