# deca

A static, single-page site for a Collegiate DECA chapter's ICDC timeline:
chapter milestones and official DECA deadlines, presented as two HTML
tables. `index.html` is the live GitHub Pages site
(`vm2027.github.io/deca/`), served directly from `main` — there is no
build step, no data pipeline, and no CI. `index1.html` (an old backup)
and `index2_files/` (orphaned Word-export assets) used to sit alongside
it but were removed as unreferenced dead weight — see git history if
either is ever needed again.

This repo is deliberately kept static-only: no Python scripts, no
GitHub Actions workflows, no generated output. Keep it that way — if a
change seems to need automation, that's a signal to reconsider the
change rather than add tooling to this repo.

## Copilot review before merging

Same practice as `vm2027/news`: after opening a PR, call
`request_copilot_review` and wait for its review comment before
merging. Do not merge solely because there's no merge conflict.

Branch protection on `main` is enabled (require a pull request before
merging, restrict force pushes, restrict deletions) — confirmed via
Settings → Branches. No required status checks or required reviewer
count, since this repo has no CI and Copilot review is a manual,
advisory step rather than a blocking check.

## What to actually check when editing the timeline

The whole value of this page is that its two tables are accurate and
internally consistent. Since there's no automated check for this
(deliberately -- see above), verify by hand before merging any date
change:
- Rows within each table stay in chronological order.
- A date that appears in both tables (e.g. the Feb 15 dues deadline,
  the Mar 9 registration/hotel deadline) matches exactly between them.
- Dates are real calendar dates (no Feb 30, etc.).
- The table still renders reasonably on a narrow/mobile viewport --
  this page has had mobile table-rendering issues before.
