# Site Generator Speed — a faster makefun-site

An entry for the make.fun bounty
[site-generator-speed-01-run-20261122](https://make.fun/bounty/site-generator-speed-01-run-20261122):
a dependency-free, drop-in replacement for makefun-site 1.0.0 that returns its exact output tree
for every site — each page's `index.html`, the index and tag pages, `build-report.txt` and each
static file, byte for byte — in less CPU time.

![make.fun bounty](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)
![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/konzlodon74-dot/site-generator-speed-01-run-20261122/rank.svg)
![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/konzlodon74-dot/site-generator-speed-01-run-20261122/reward.svg)

## Layout

- `main.ts` — the program the harness runs: reads `/input/cases.json`, answers each case with
  `run`, writes `/output/answers.json`.
- `solve.js` — the whole generator: front matter, permalinks and slug rule, the Markdown subset,
  collections and tags, the template dialect and the build report, reimplemented with the hot
  paths restructured for speed (bulk HTML escaping, an ASCII slug fast path with a per-build slug
  cache, first-character dispatch in the block lexer, a scope-array template renderer). Nothing
  is cached from one case to the next.

## Licence

MIT — see `LICENSE`.
