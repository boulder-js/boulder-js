# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Structure

This is an umbrella directory containing independent git repositories for the BoulderJS community. Each local subdirectory maps to a GitHub repo of the same name in the `boulder-js` org (e.g. `website/` → `boulder-js/website`):

- **`website/`** — Astro SSR website deployed to Cloudflare Pages. Has its own `CLAUDE.md` with full development instructions.
- **`events/`** — GitHub issues-based event management. Events are created as GitHub issues; GitHub Actions automate ICS calendar generation and Bluesky social posts.
- **`talks/`** — GitHub issues-based talk proposals. Community members submit talks as GitHub issues, which are voted on and scheduled into events.
- **`jobs/`** — GitHub issues-based job postings.

The root `.gitignore` ignores everything except `README.md` and `.claude/` — each subdirectory is its own independent git repo.

## How the Projects Connect

1. **Events as GitHub Issues**: Events are created as issues in the `boulder-js/events` GitHub repo (mirrored in `events/`). When labeled `Approved`, automated workflows post to Bluesky.
2. **ICS Calendar**: A daily GitHub Actions cron job in `events/` uses `gitevents/ics` to regenerate `events/events.ics` from open GitHub issues.
3. **Website Data**: The website fetches event, talk, and speaker data at runtime via the `gitevents-fetch` npm package, which queries the GitHub GraphQL API. No data is stored in the website repo itself.
4. **Locations**: `events/locations.json` defines venue data (id, name, address, coordinates) referenced by event issues.

## GitHub Automation (events/)

Key workflows in `events/.github/workflows/`:
- `gitevents.yml` — Validates event issue structure on push/PR/issue open via `gitevents/action`
- `ics.yml` — Daily cron regenerates `events.ics` calendar file
- `bluesky.yml` — Posts to Bluesky when an event issue is labeled `Approved ✅`
- `inclusive-org.yml` — Auto-invites contributors to the GitHub org via `gitevents/inclusive-org`

## Website Development

See `website/CLAUDE.md` for full details. Quick reference:

```bash
cd website
npm install
npm run dev        # http://localhost:4321
npm run build
npm run lint
npm run pretty
npx playwright test
```

Requires `GH_PAT` env var (GitHub PAT for `boulder-js` org with public repo read + members read access).

## Code Style (website)

- No semicolons, single quotes, no trailing commas (Prettier)
- SolidJS `.jsx` components with PascalCase naming and named exports
- Tailwind CSS v4 utility classes; use `clsx` for conditionals
- Do not manually sort event data — `gitevents-fetch` handles ordering
