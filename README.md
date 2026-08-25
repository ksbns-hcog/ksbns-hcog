# 2027 한국뇌신경과학회 고등인지분과 동계 워크샵

Workshop website source. Published via GitHub Pages at:
https://hkim09.github.io/ksnbs_hcog/

## Editing this site

This is plain HTML — no build step. Styling uses the Tailwind CSS **Play
CDN** (`<script src="https://cdn.tailwindcss.com">` in `index.html`), so
you style things by adding utility classes directly on elements (e.g.
`class="text-2xl font-bold text-indigo-700"`) rather than writing CSS.
`style.css` only holds the Korean font override. Play CDN is intended for
prototyping — fine for a small, low-traffic workshop page, but if this
site ever needs heavier traffic/performance, switch to a compiled Tailwind
build.

To update content, ask Claude Code to edit `index.html` (text, dates,
links, or Tailwind classes for styling), then commit and push:

```
git add -A
git commit -m "update: ..."
git push
```

Changes appear on the live site within a minute or two of pushing.

## Structure

- `index.html` — all page content
- `style.css` — styling
- `images/` — photos for the gallery section
