# Repo notes for Claude

Company marketing site for **Hoshiko Tech Ltd.** — https://www.hoshiko.tech

Static site served via GitHub Pages, styled with Tailwind (CDN), no build step.
English pages at the root; Japanese equivalents under `/ja/`.

## Conventions

- **This repo (marketing site):** stays on **GitHub Pages**, static, no build.
- **Client project sites:** default to **Cloudflare** (Pages + Workers), matching
  the existing `sushi-masa` project. Reach for Workers / D1 / KV / R2 / Turnstile
  whenever a client needs forms, bookings, online ordering, accounts, or any
  server-side logic — things GitHub Pages can't host.
- **Client onboarding materials** (intake questionnaires, form specs) live under
  `templates/`, organised by business type (e.g. `templates/sushi/`).
