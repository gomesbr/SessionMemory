---
type: project-rules
project: p6planner
updated: 2026-10-24
tags: [project/p6planner, rules]
---

# P6 Planner - Project Rules

> Seeded from `P6Planner\.planning\PROJECT.md`, `REQUIREMENTS.md`, `ROADMAP.md`, `STATE.md`, `package.json` and the Oct 24 2026 trial. Approved by Fabio Oct 24 2026.

## ALWAYS DO

- Treat the audience as Patti's pickleball group of about 20 adults over 60 with low tech appetite: no install, nothing to learn, big obvious controls.
- Keep the stack fixed: Vite + React + TypeScript, Cloudflare Pages hosting, Cloudflare Pages Functions for admin writes and OpenAI phrase generation, Supabase Postgres for data.
- Keep the fixed player link `p6planner.pages.dev/p6` working; it always shows the current week's cards and is the link shared with players.
- Keep per-week links working (form `/week/october-19-2026`); old links must never break.
- Compute "today" and week dates in `America/New_York`. A week stays current until its last play day has passed.
- Run `npm run typecheck`, `npm run build`, `npm run test:weeks` and `npm run test:studio` before every handoff; add or extend a smoke script for new behavior.
- Verify UI on a phone-width viewport as well as desktop; the mobile layout must avoid an unusable wide table.
- Code style: Ponytail full mode (never ultra), minimal, dense, idiomatic, no golfing.
- Work on a feature branch and verify on a Cloudflare preview deploy before asking to ship.

## NEVER DO

- Never push or merge to `main` without Fabio's approval of that specific change: the Pages project is connected to GitHub, so `main` deploys live to `p6planner.pages.dev`.
- Never add player accounts, passwords, PINs, phone or email collection, or SMS sending.
- Never let the public page edit any row except the selected player's own row.
- Never expose the admin password, Supabase service keys or the OpenAI key to the browser; they stay server-side in Pages Functions and Pages secrets.
- Never build a complex calendar or recurring scheduling engine; schedule periods stay flexible and simple.
- Never add a dependency without asking.

## CONDITIONAL RULES

- If a change touches the database schema or live Supabase data, stop and get Fabio's approval first.
- If a change affects admin (`/admin`), keep it limited to what Patti does: players, schedule periods, sessions, default location, availability, phrase text, and the copyable group-chat summary.
- If phrase-of-the-week generation changes, generate only when Patti asks, and keep use / edit / replace available.
- If a change is cosmetic or copy-related, send it as a numbered packet for approval by number.

## SCOPE NOTES

- Applies only to `p6planner` (repo `gomesbr/P6Planner`, local `D:\Fabio\Cursor AI projects\Projects\P6Planner`).
- `.planning\STATE.md` still says Phase 1 (June 8 2026) and is stale; the app is live. Updating it is a separate, approved task.
