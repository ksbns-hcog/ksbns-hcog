---
name: new-workshop-year
description: Scaffold a new year's workshop page in this KSBNS-HCOG archive site (e.g. "set up 2028", "create the 2029 workshop page"). Use when the user wants to add a brand-new year folder to the archive.
---

Scaffold a new year folder for the workshop archive.

1. Ask the user which year to create (e.g. `2028`) if not given, and whether program/abstract PDFs already exist to source content from (if so, ask where they are).
2. Pick the most recent existing year folder (currently the highest-numbered of `2023/`, `2024/`, `2026/`, `2027/`) as the structural template — copy its layout: `index.html`, `style.css`, `logo.jpg`, `images/` (with a `.gitkeep` if empty).
3. Reset the copied `index.html` content for the new year: clear out prior-year-specific text (dates, speakers, sponsors, program details) while keeping the overall structure/sections. If source PDFs were provided, populate content from them; otherwise leave placeholders and note what's missing rather than inventing facts.
4. Keep every asset reference inside the new folder **relative** (`style.css`, `images/...`, `#anchor`) — never root-absolute (`/style.css`) and never pointing into another year's folder. This is the repo's core invariant (see CLAUDE.md).
5. Add a link/card to the new year from the root `index.html` hub, following the existing card pattern for other years.
6. When the new year's program/abstract PDFs are added, gate their download links the same way other years do: give each `<a href="....pdf">` a `pdf-gate` class, and add an inline `<script>` block at the bottom of the page (before `</body>`) with `const PDF_PASSWORD = 'neurosplash20XX'` (XX = the new year's 2-digit year) that intercepts clicks, `prompt()`s for the password, and only `window.open`s the real `href` on a match. Copy the exact script body from an existing year (e.g. `2026/index.html`) rather than rewriting it. Note this is a deterrent, not real security — the repo is public.
7. Do not modify any other year's folder.
8. Remind the user to review content accuracy against the source PDFs before committing, then commit/push per the repo's normal workflow (`git add -A && git commit -m "..." && git push`) — only if the user asks you to commit.
