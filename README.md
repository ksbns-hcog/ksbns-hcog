# 한국뇌신경과학회 고등인지분과 워크샵 아카이브

Workshop website archive. Published via GitHub Pages at:
https://hkim09.github.io/ksnbs_hcog/

Each year's workshop has its own fully self-contained homepage in a
year-named folder (`2027/`, `2026/`, ...). The root `index.html` is just an
archive hub linking to each year.

## Structure

```
index.html          — archive hub (links to each year)
2027/                — upcoming winter workshop (content in progress)
2026/                — 2026 winter workshop (past, archived from PDFs)
2024/                — 2024 summer workshop "Neurosplash" (past, archived from PDFs)
2023/                — 2023 summer workshop "Neurosplash" (past, archived from PDFs)
  index.html
  style.css
  program*.pdf / abstract_booklet.pdf  — canonical source PDFs for that year
```

"Neurosplash" is the historical banner/brand name this workshop series used
on promotional materials (2023–2026); it is not a separate event.

Each past year's page was built from the organizers' own program/abstract
PDFs (originally dropped in the repo root, then copied into that year's
folder under clean filenames). Facts not stated in the source PDFs (e.g. an
unnamed invited speaker) were left out rather than guessed — check the PDFs
directly if something needs filling in.

**Each year folder is independent.** A year's `index.html` only ever
references files inside its own folder using relative paths (e.g.
`style.css`, `images/photo1.jpg`, `#section-anchor`) — never `/style.css`
or anything referencing another year. This means:

- The whole `ksnbs_hcog` repo/site can be moved or renamed without breaking
  any year's page.
- Redesigning one year (colors, layout, adding a new CSS file, etc.) never
  affects any other year, since nothing is shared between year folders.

When adding a new year, copy an existing year's folder as a starting point
(or ask Claude Code to build a new one from scratch), keep all its asset
references relative and folder-local, and add a link to it from the root
`index.html` hub.

## Editing this site

Plain HTML — no build step. Styling uses the Tailwind CSS **Play CDN**
(`<script src="https://cdn.tailwindcss.com">`), so you style things with
utility classes directly on elements (e.g. `class="text-2xl font-bold
text-indigo-700"`) rather than writing CSS. Play CDN is intended for
prototyping — fine for a small, low-traffic site, but if this ever needs
heavier traffic/performance, switch to a compiled Tailwind build.

To update content, ask Claude Code to edit the relevant year's
`index.html`, then commit and push:

```
git add -A
git commit -m "update: ..."
git push
```

Changes appear on the live site within a minute or two of pushing.
