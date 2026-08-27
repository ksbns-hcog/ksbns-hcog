# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A no-build static site archiving the KSBNS (한국뇌신경과학회) 고등인지분과 workshop pages, deployed to GitHub Pages via `.github/workflows/pages.yml` (Actions-based deploy, triggers on push to `main`). Root `index.html` is just a hub linking to each year's folder (`2027/`, `2026/`, `2024/`, `2023/`).

## Year-folder independence (critical rule)

Each year folder (`2023/`, `2024/`, `2026/`, `2027/`, ...) is fully self-contained: `index.html`, `style.css`, `logo.jpg`, plus that year's source PDFs. A year's `index.html` must only reference files inside its own folder using **relative paths** (`style.css`, `images/photo1.jpg`, `#anchor`) — never a root-absolute path (`/style.css`) or a path into another year's folder. This lets any year be moved, renamed, or redesigned without touching the others or the root hub.

When adding a new year: copy an existing year's folder as a starting point, keep all paths relative/folder-local, and add a link to it from the root `index.html` hub. (See the `new-workshop-year` skill.)

## Styling

Plain HTML, no build step. Styling is Tailwind CSS via the **Play CDN** (`<script src="https://cdn.tailwindcss.com">`) — style with utility classes directly on elements, don't write separate CSS rules or introduce a build pipeline. Play CDN is prototype-grade; that's an accepted tradeoff for this low-traffic site.

## PDF access gate

The repo is a **public** GitHub repo, so files (including PDFs) are always fetchable directly by URL regardless of any client-side gating — this is a deterrent for casual visitors, not real access control. Program/abstract PDF links (`class="pdf-gate"`) are intercepted by an inline `<script>` at the bottom of each year's `index.html` that `prompt()`s for a password before `window.open`-ing the real `href`. Password convention: `neurosplash20XX` (XX = that year's 2-digit year), stored in plaintext as `PDF_PASSWORD` in that year's script block — different password per year. When adding a new year's PDFs, copy this pattern and use that year's password.

## Content accuracy

Past years' pages are built from the organizers' own program/abstract PDFs (kept in each year's folder as the canonical source). If a fact isn't in the source PDF (e.g. an unnamed speaker), leave it out rather than guessing — check the PDF directly.

## Workflow

No PRs/branches — commits go directly to `main` and deploy automatically:

```
git add -A
git commit -m "update: ..."
git push
```
