# SITEMAP — Tradetron surfaces

Derived from the live app's public routes (`routes/guest.php`) and view tree
(`resources/views/{guest,auth}`). This is what exists today — the *content and
surfaces* to redesign. Replace the styling entirely with the new editorial language;
do not preserve the current look.

The app is segmented by **layout shell** (`layouts/v1/{marketing, guest, user, ...}`),
so the public surface and the logged-in app are already separate. That's why Phase 1
(below) can ship without touching the app.

---

## Phase 1 — BUILD FULLY (public, no auth required)

### Marketing / landing
- `/` — primary landing (home)
- `/us` — US landing variant
- `/signup` — marketing signup landing
- `/free-trading-app`
- `/crypto-trading`
- `/nri-algo-trading`
- `/switch-to-tradetron` — competitor switch page

### Product / info
- `/features` — features
- `/pricing` and new-pricing — plans & pricing tiers
- `/marketplace` — public strategy marketplace (browse/listing)
- top strategies, top creators, featured strategy, public strategy stats
- `/paper-trading`
- backtest / "what is backtest" explainer
- scalping, straddle strategy (strategy explainer pages)
- services, user cases / case studies, webinar
- `/faq` (+ single FAQ)

### Legal
- `/privacy`, `/terms`, `/terms-us`

### Auth
- `/login`
- `/register`
- forgot-password / reset (`auth/passwords`)
- email + mobile OTP verification (`/auth/verify/*`, `/auth/verification/{id}`)
- social login buttons (Google, Facebook, + broker logins) — style the buttons,
  not the OAuth flows

### Component library (used across all of the above)
top nav/header **with light/dark toggle**, footer (multi-column: Product / Learn /
Company / Legal), buttons, cards, forms/inputs, selects, tables, badges/tags, modals,
tabs, alerts/toasts, pagination, empty states.

---

## Reference only — DO NOT PRODUCTIONIZE (logged-in app)

Produce labeled *functional-variant* mockups as integration targets, not a build:
- **Dashboard** — deployed strategies overview, P&L, positions
- **Reports / data-table page** — dense tabular data, filters, pagination
- **Strategy Builder (ASB) shell** — the strategy authoring canvas

These are the data-dense screens where the **functional** mode (higher contrast, tighter
density, sans for numbers) matters more than expressiveness. Redesigning these for real
is Claude Code's job, against the live app — the tool only needs to show the target.

---

## Notes for the designer
- The footer IA visible in `reference/` (Product: Marketplace/Build/Backtest/Deploy/
  Pricing · Learn: Manual/Tutorials/Community/Blog · Company: About/Careers/Press/Contact
  · Legal: Privacy/Terms/Security/Status) is the intended information architecture — use it.
- Real content (pricing numbers, broker list, stats, testimonials) needs legal/content
  review — use clearly-marked placeholders, do not fabricate.
