# Rebuild plan: Real Spice v1

**Launch:** Friday 29 January 2027. Started 11 November 2026, working a few sittings a week.
**Stack:** HTML, CSS and vanilla JavaScript. No framework, no build step.
**Hosting:** GitHub Pages (free, deploys on every push to `main`).

> **What changed:** the first plan was a one-week sprint to 18 November 2026. Once we started,
> the Figma designs turned out to be more detailed than the original issues, so the work was
> split into smaller issues and grouped into milestones that act as sprints. `menu.html` was
> dropped: the menu now lives on the home page.

## Scope

**In v1:** a fast, mobile-first menu home page with search and filters, built from one JSON file;
an "Open now" badge; a contact page with find us, hours, delivery, allergy info and about; and
real ordering handed off to the restaurant's existing ordering system or a phone call.

**After v1:** a **demo** basket and checkout that follow the Figma designs (`docs/02` to `docs/05`).
It's clearly labelled as a demo: no real orders, no payments, no card fields.

**Not planned:** user accounts, a CMS, real payments.

## Milestones

Each milestone is a sprint. Each issue in it is one branch and one small PR.

| # | Milestone | Due | Issues | What you'll learn |
|---|---|---|---|---|
| 1 | HTML done | Fri 27 Nov 2026 | #19–#28 (parent #3) | landmarks, headings, forms, tables, accessible markup |
| 2 | Looks like the design | Fri 11 Dec 2026 | #29–#38 (parents #4, #5) | flexbox, grid, `position: sticky`, responsive layout |
| 3 | Real menu data | Fri 8 Jan 2027 (includes a Christmas break) | #6, #7, #8 | JSON data modelling, `fetch`, DOM building, IntersectionObserver |
| 4 | Launch | Fri 29 Jan 2027 | #9–#13 | events and filtering, `Date`, Lighthouse, cross-device QA |
| 5 | Demo ordering | after launch, no date yet | #43–#53 (parent #14) | state management, `localStorage`, `<dialog>`, form validation |

Issues #6–#13 are split into smaller ones just before we start them, so they reflect what we've
learned by then.

## Decisions so far

- **The menu is the home page.** There's no separate `menu.html`.
- **The Figma design is the source of truth** for content and layout.
- **One flat £2.50 delivery fee.** The original site lists three zones but never says which
  areas are in which, so zones can't help a customer.
- **Prices are stored in pence**, in both the HTML (`<data value="1099">`) and the JSON.

## How we work on each issue

1. Start from an up-to-date `main`: `git switch main`, then `git pull`.
2. Create a branch: `git switch -c 7-render-menu`
3. Build it in small commits. Before each one: save, run the
   [validator](https://validator.w3.org/nu/), then check `git diff --staged`.
   Use the message format `Verb what changed (#7)`.
4. Open a pull request that says `Closes #7`.
5. Wait for the review, fix what comes up, then **Squash and merge**.
