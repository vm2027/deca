---
name: code-review
description: Repo-specific context for reviewing changes to the DECA ICDC chapter timeline site (a static index.html, no build step).
---

# Reviewing changes to this repository

`index.html` is a single static page with two hand-maintained HTML
tables (a chapter milestone timeline, and official DECA deadlines).
There is no build step, no server, and no generated output -- what's
committed to `index.html` on `main` is exactly what's live at
`vm2027.github.io/deca/`.

## Checks specific to this repo

- **Chronological order.** Rows within each table should read in
  non-decreasing date order top to bottom. Flag any edit that
  reorders or inserts a row out of sequence.
- **Cross-table date consistency.** Some dates are meant to be
  identical across both tables (e.g. the roster/dues deadline, the
  registration + hotel deadline). If a change touches one occurrence
  of such a date, check whether the other table's matching row needs
  the same update.
- **Valid calendar dates.** Watch for typos that produce an invalid or
  clearly wrong date (wrong year, day that doesn't exist in that
  month, etc.).
- **Mobile table rendering.** This page has previously had tables
  break or overflow on narrow viewports. Flag CSS/table-structure
  changes (column counts, widths, wrapping) that could reintroduce
  that.
- **Don't suggest adding a build step, framework, or automated test
  suite.** This repo is deliberately kept as a single static file with
  no tooling -- that's a choice, not an oversight.
