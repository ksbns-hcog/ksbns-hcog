# 한국뇌신경과학회 고등인지분과 워크샵 아카이브

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

**Each year folder is independent.** A year's `index.html` only ever
references files inside its own folder using relative paths (e.g.
`style.css`, `images/photo1.jpg`, `#section-anchor`) — never `/style.css`
or anything referencing another year. This means:

When adding a new year, copy an existing year's folder as a starting point
(or ask Claude Code to build a new one from scratch), keep all its asset
references relative and folder-local, and add a link to it from the root
`index.html` hub.
