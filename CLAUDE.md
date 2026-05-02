# CLAUDE.md

Notes for future Claude sessions on this repo.

## What this is

Personal blog at <https://alexiuskomnin.github.io/> — Hugo static site, PaperMod theme, deployed via GitHub Actions to GitHub Pages.

## Stack

- **Hugo extended** (pinned to a version in `.github/workflows/hugo.yml` — `HUGO_VERSION` env)
- **PaperMod** theme as a Git submodule at `themes/PaperMod`
- **GitHub Actions** workflow at `.github/workflows/hugo.yml` builds on push to `master` and deploys to Pages

## Layout

- `hugo.toml` — site config (theme params, menu, syntax highlighting style)
- `content/posts/<slug>/index.md` — blog posts as **page bundles** (each post is a folder; images live next to `index.md`)
- `content/archives.md` — archive page (uses PaperMod's `archives` layout)
- `archetypes/default.md` — template for `hugo new` command
- `themes/PaperMod` — theme submodule, do not edit directly
- `static/` — root-level static assets (favicon, etc.) — create if needed

## Common tasks

| Task | Command |
| --- | --- |
| New post | `hugo new content posts/<slug>/index.md` |
| Local preview (incl. drafts) | `hugo server -D` |
| Update theme | `git submodule update --remote themes/PaperMod` |
| Build locally | `hugo --minify` (output in `public/`) |

## Deployment

- Push to `master` → workflow builds → deploys to Pages
- One-time setup in repo settings: **Settings → Pages → Source → GitHub Actions**
- Pages env URL appears as the `deploy` job's `page_url` output

## Conventions

- Posts are folders (page bundles), not single `.md` files — keeps images co-located
- Drafts: `draft: true` in front matter, hidden from production builds
- Code blocks: triple-backtick with language tag, Chroma highlighter, theme set in `[markup.highlight]` of `hugo.toml`
- Goldmark `unsafe = true` is on so raw HTML in markdown works (use sparingly)

## Things that have NOT been set up yet

- Custom domain (would need `static/CNAME` + DNS)
- Comments (would plug into Giscus or similar)
- Analytics
- Search (Hugo can output a JSON index — `outputs.home` already includes `JSON` — but no UI is wired up)
- Favicon / og:image
- LinkedIn / email social icons (commented out in `hugo.toml`)
