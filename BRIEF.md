# BRIEF — Tradetron redesign: design system + public surface (light + dark)

## What Tradetron is
An algorithmic-trading platform. Users build, backtest, and deploy strategies that
trade real money through their broker. Audience: retail and serious/semi-pro traders,
India + global.

## Your job
Produce a complete, self-contained **design system** and build out the
**public / marketing / auth surfaces** in it, in **both light and dark mode**. You are
the source of truth for the visual language. You are **not** redesigning the logged-in
trading app — for that, produce only a few clearly-labeled reference mockups.

## Aesthetic (locked — continue the landing page in `reference/`)
Editorial / luxury-print. Serif display headlines with italic serif accents; warm cream
(not pure white) ground; rust/terracotta accent; hairline rules; small-caps numbered
section markers ("— 03 / THE PLUMBING"); black pill primary buttons, outlined pill
secondary; generous whitespace. Confident, understated, premium — the opposite of a
neon SaaS dashboard.

## Dark mode (specific)
Carry the **same editorial language** into dark — a warm, "dark-academia" dark: deep
warm charcoal / espresso ground, off-white/cream text, terracotta accent preserved
(optional muted gold secondary). Do **NOT** do black + neon trading-green — that fintech
cliché is explicitly rejected. Theme toggle in the top nav, choice persisted. Both modes
are the same tokens flipped.

## Output format (hard constraints — this gets integrated into an existing app)
- Plain semantic **HTML + one CSS system**. ALL design decisions as **CSS custom
  properties**, so dark mode = a single attribute/class on `<html>`.
- **Vanilla JS only**, and only for the theme toggle (localStorage).
- Do **NOT** build a React / Next / Vue / Tailwind SPA. Target is a **Laravel Blade**
  app on **Bootstrap 4** with a **webpack/laravel-mix SCSS** pipeline. Everything must
  be expressible as Blade partials + SCSS. Assume no JS framework.
- Ship **one tokens file** (color, type scale, spacing, radius, shadow; both modes) as
  the source of truth.
- Name fonts explicitly; prefer Google-Fonts serifs (self-hostable). Flag anything
  licensed.

## Two modes of the system (important)
- **Expressive** (marketing/public): full editorial treatment above.
- **Functional** (data-dense app screens): same palette/tokens, but higher contrast,
  tighter density, clean sans for tabular/numeric data. Readability beats expressiveness
  here. Include this variant even though you're not building the app.

## Build fully (light + dark) — see SITEMAP.md "Phase 1"
Marketing/landing pages; pricing; features; about/company; contact; auth (login,
register, forgot-password, OTP/verify). Component library: top nav (with toggle) +
footer, buttons, cards, forms/inputs, tables, badges, modals, tabs, alerts, pagination,
empty states.

## Reference only (do NOT productionize) — see SITEMAP.md "Reference"
2–3 labeled mockups of the logged-in app in the functional variant — a dashboard, a
reports/data-table page, the strategy-builder shell. Integration targets, not deliverables.

## Don'ts
- Don't invent product claims, stats, or broker lists — use clearly-marked placeholders
  (real numbers need legal review).
- Don't build backend / auth / API logic.
- Don't assume any framework beyond the SCSS/Bootstrap target.

## Deliverable shape
`/tokens`, `/components`, `/pages`, `/reference` (app mockups), and `STYLEGUIDE.md`
documenting tokens, type scale, spacing, and component usage in both modes.
