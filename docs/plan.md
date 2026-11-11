# Rebuild plan: Real Spice v1

**Deadline:** Wednesday 18 November 2026 (one week from 11 November).
**Stack:** HTML, CSS and vanilla JavaScript. No framework, no build step.
**Hosting:** GitHub Pages (free, deploys on every push).

## Scope

**In v1:** a fast, mobile-first site with a home page, a searchable and filterable menu built
from one JSON file, an "Open now" badge, clear delivery and allergy info, contact with a map,
and ordering handed off to the restaurant's existing ordering system or a phone call.

**Not in v1:** our own basket or checkout, payments, user accounts, a CMS. (A practice basket
is a stretch goal at the bottom.)

## Issues, in order

| Day | # | Issue | What you'll learn |
|---|---|---|---|
| Wed 11 | 1 | Project setup and first deploy | git, folder structure, GitHub Pages |
| Wed 11 | 2 | Design foundations: wireframe and tokens | mobile-first thinking, CSS custom properties |
| Thu 12 | 3 | Semantic HTML for the home page | landmarks, headings, accessible markup |
| Thu 12 | 4 | Header and mobile navigation | flexbox, a JS toggle, `aria-expanded` |
| Fri 13 | 5 | Style the home page | layout, hero, responsive images |
| Fri 13 | 6 | Turn the menu into `menu.json` | data modelling, single source of truth |
| Sat 14 | 7 | Render the menu from JSON | `fetch`, DOM building, templates |
| Sat 14 | 8 | Sticky category bar with scroll-spy | `position: sticky`, IntersectionObserver |
| Sun 15 | 9 | Menu search and filters | events, filtering arrays, debouncing |
| Sun 15 | 10 | "Open now" badge | `Date`, edge cases (closing at midnight) |
| Mon 16 | 11 | Ordering, delivery and contact | third-party embeds, `tel:` links, maps |
| Tue 17 | 12 | Accessibility, performance and SEO pass | Lighthouse, contrast, JSON-LD |
| Wed 18 | 13 | Launch: cross-device QA and README | testing checklist, writing docs |

**Stretch (after v1):** a practice basket stored in `localStorage`, which totals the order and
applies the delivery minimums.

## How we'll work on each issue

1. Create a branch: `git switch -c 7-render-menu`
2. Build it in small commits.
3. Open a pull request that says `Closes #7`.
4. I review it like a senior engineer would, you fix what comes up, then merge.
