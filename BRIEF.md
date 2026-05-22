# BRIEF — Tradetron redesign: design system + public surface (light + dark)

## What Tradetron is
An algorithmic-trading platform. Users build, backtest, and deploy strategies that
trade real money through their broker.

## Positioning (DECIDED — read this before anything else)
Target user: the **aspiring retail trader** (pays ~₹300/month) who wants to *feel* like a
serious, successful trader. Position = **institutional-grade power, made accessible** —
"the power of a professional trading desk, for the price of a coffee." Aspirational, but
inclusive.

**WIN CONDITION:** a ₹300 retail user feels **capable and elevated — like a pro** — not
intimidated or out of their depth. Aspiration, not exclusion.

Guard against the three failure modes that kill this bridge:
- **Intimidation.** "Institutional" can read as "not for me." The user must feel the tool
  makes *them* powerful — never that it's built for someone above their level.
- **Lost clarity.** Premium/editorial tempts toward sparse and implicit. Keep
  retail-grade clarity: obvious primary CTAs, plain-language copy, an unmissable
  "how do I start" path. Premium ≠ obscure.
- **Stripped trust signals.** Keep the retail reassurances that convert this segment —
  free paper trading, "no code", social proof / user numbers, accessibility — *under* the
  premium skin. Elevate the wrapper; don't delete the substance.

## Your job
Explore **2–3 genuinely divergent directions** for the position above, then (after we
pick one) build it out. You own the visual language and the public/marketing/auth
surfaces. You are not rebuilding the logged-in app — but each direction must prove itself
on one data-dense app screen (see Deliverable).

## Aesthetic starting point (one reference, NOT the only answer)
`reference/` holds a landing already designed in a warm editorial / luxury-print language
(serif display + italic accents, cream ground, rust/terracotta, hairline rules, small-caps
section markers, black pill CTAs). It's a strong candidate for "institutional, made
accessible" — but it's ONE direction. At least one other direction must be a genuinely
different expression of the *same position* (e.g. a precision / "modern terminal" take, or
a confident-minimal take) — not three shades of the same thing. Avoid the generic
"AI-editorial landing" sameness; earn distinctiveness through a trading-specific point of
view.

## Dark mode (specific)
Each direction ships light AND dark from ONE set of CSS custom properties (toggle in the
nav). Dark must NOT be black + neon trading-green — that cliché is out. (For the editorial
direction, dark = warm "dark-academia": espresso/charcoal + cream + terracotta.)

## Output format (hard constraints — this gets integrated into an existing app)
- Plain semantic HTML + one CSS system per direction. ALL design decisions as CSS custom
  properties, so dark mode = a single attribute/class on `<html>`.
- Vanilla JS only, and only for the theme toggle (localStorage).
- NO React / Next / Vue / Tailwind SPA. Target is **Laravel Blade + Bootstrap 4 + a
  webpack/laravel-mix SCSS pipeline**; everything must port to Blade partials + SCSS.
- One tokens file per direction as its source of truth.
- Name fonts explicitly; prefer self-hostable Google fonts. Flag anything licensed.

## Two modes within each direction
- **Expressive** (marketing/public): full character.
- **Functional** (data-dense app): same tokens, higher contrast, tighter density, clean
  sans for tabular/numeric data. Readability beats flourish. **This is where "feels like a
  pro, not intimidated" is won or lost.**

## Deliverable — TWO STAGES
**Stage 1 (now): 2–3 distinct directions.** For EACH direction provide: a tokens sketch
(light+dark), the landing hero, **one data-dense app screen** (functional variant — e.g.
dashboard or strategy builder), and 2–3 core components (nav with toggle, button, card).
Enough to judge the *system* on both expressive and functional ground — not a full build.
Put each under `/directions/<name>/` with a one-paragraph rationale tying it to the
positioning + win condition.

**Stage 2 (after we pick one):** build the chosen direction fully across the public/auth
surfaces in `SITEMAP.md`, into `/tokens`, `/components`, `/pages`, with `STYLEGUIDE.md`.

## Don'ts
- Don't fabricate product claims, stats, broker lists, or testimonials — clearly-marked
  placeholders only (real numbers need legal review).
- Don't build backend / auth / API logic.
- Don't assume any framework beyond the SCSS/Bootstrap target.
