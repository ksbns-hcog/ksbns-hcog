# 한국뇌신경과학회 고등인지분과

Each year's workshop has its own fully self-contained homepage in a
year-named folder (`2027/`, `2026/`, ...). The root `index.html` is just an
archive hub linking to each year.

## TODO

Delete item once it is done.
- 연도별 개최내역을 정리한 내용이 있어 보내드립니다. 필요한 정보를 골라 사용하시고, 추가로 더 필요한 정보가 있다면 알려주세요.
- 위(banner)에 예쁜 brain related background 이미지
- 페이지 맨 아래나 맨 위 (혹은 옆에 컬럼으로?) 후원사들의 로고들을 쭉 깔아

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
