# tt-redesign — Tradetron redesign workspace

This repo is the **output target for the design tool** and the **integration spec**
for Claude Code. It is **not** the Tradetron application. The real app (`tt-web`,
Laravel 6 / Blade / Bootstrap 4 / webpack-mix) is integrated separately, on staging,
using whatever lands here as the spec.

## Division of labor

- **Design tool** — owns the visual language. Produces the design *system* (tokens,
  components, light + dark) and builds out the public / marketing / auth surfaces in
  it. Does **not** rebuild the logged-in trading app (reference mockups only).
- **Claude Code** — owns integration. Ports the system into the live Laravel app,
  against staging, screen by screen, with real app context and browser access.

## Read in this order

1. `BRIEF.md` — the job + the hard output constraints. Start here.
2. `SITEMAP.md` — the real page inventory (derived from the app's routes), grouped
   into what to build vs. reference-only.
3. `reference/` — the locked aesthetic (the landing page already designed in this
   language). Continue this look; do not invent a new one.

## How the tool should use this

It does not need the app's source code (it can't run a Laravel app, and the source
is backend-coupled). It needs surfaces + content + the target look — all here. Design
from `SITEMAP.md` and `reference/`, honor `BRIEF.md`'s output format, push results to
`/tokens`, `/components`, `/pages`, `/reference`, and document in `STYLEGUIDE.md`.
