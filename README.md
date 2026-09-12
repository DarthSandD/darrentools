# VoltWorks Power — darrentools

Live site: https://darthsandd.github.io/darrentools/ (GitHub Pages, serves `index.html`).

Single-file electrical calculator suite: feeder voltage drop, transformer
sizing + short-circuit, cable sizing, cooling load, pipe + pump, beam/column,
live load-study slider, SLD canvas builder, and a generated engineering report.

## Input persistence

Every input (numbers, selects, the load slider) autosaves to the site's own
`localStorage` (key `voltworks-power-v1`, debounced 300ms) and restores before
the first calculation on every load — refresh-safe, no account, no backend.
The ↩ Reset button in the header clears saved state back to defaults.

## Deploy

Local `master` pushes to remote `main` (`git push origin master:main`).
Pages rebuilds in ~1–2 min — verify live with:
`curl -s https://darthsandd.github.io/darrentools/ | grep -c vwRestore` (expect 2).
