# Tachles Website - Project State

> Living document. Read this first before working on the project.

Last updated: 2026-06-28

## What this is

Marketing site for Tachles - a margin-protection product for small e-commerce stores. Single-page static site (self-contained HTML) deployed on GitHub Pages. Restyled from the original prototype to a navy + teal corporate look inspired by returnGO.

Repo: https://github.com/Nadavbotan/tachles-website (public)
Live: https://nadavbotan.github.io/tachles-website/
Account: Nadavbotan / nadavh52@gmail.com

## Current state

| Component | Status |
|---|---|
| Prototype (tachles_poc.html) | Done - full interactive prototype with all copy |
| Website folder (Personal/Payme/website/) | Done |
| Restyle (navy + teal, no gradient) | Done |
| GitHub repo (public, Nadavbotan) | Done |
| GitHub Pages deployment | Done - live, HTTP 200 |

## Architecture

- Single `index.html` file, fully self-contained (CSS + JS inline, Google Fonts via CDN).
- No build step, no dependencies. Edit the file, commit, push - Pages rebuilds.
- `.nojekyll` present so GitHub serves everything as-is.
- Standalone git repo inside `Personal/Payme/website/` (isolated from JARVIS repo since `Personal/` is gitignored).

## Key decisions

- 2026-06-27 - Single-file approach (no framework, no bundler). The prototype was already self-contained and there is no reason to add complexity for a marketing site.
- 2026-06-27 - Restyle was CSS-only: swapped gradient buttons to solid navy, gradient text to solid teal, cooled background tones, toned down glow blobs. Zero copy or JS changes.
- 2026-06-27 - Public repo on the personal Nadavbotan account, not the work nadavhacham account.

## How to update

```bash
cd Personal/Payme/website
gh auth switch --user Nadavbotan
# edit index.html
git add -A && git commit -m "description" && git push
gh auth switch --user nadavhacham
```

Pages rebuilds automatically on push (takes around 30 seconds).

## Next steps

- [ ] Add a favicon and Open Graph meta tags for link previews.
- [ ] Add Hebrew version toggle or RTL-first version if needed for Israeli audience.
- [ ] Consider a custom domain if the project moves forward.
- [ ] Add analytics (Plausible or similar) if tracking interest matters.
