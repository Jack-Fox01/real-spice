# Real Spice

A faster, friendlier website for **Real Spice**, an Indian takeaway in Leven, Fife. It's built with plain HTML, CSS and JavaScript: no framework and no build step.

**Live site:** https://jack-fox01.github.io/real-spice/ (it goes live once GitHub Pages is turned on in [#1](https://github.com/Jack-Fox01/real-spice/issues/1))

> **Unofficial concept.** This is a learning and portfolio project, not the restaurant's official site.
> To order for real, go to [realspiceleven.co.uk](https://www.realspiceleven.co.uk/) or call **01333 422533**.

## The problem

The [current site](https://www.realspiceleven.co.uk/) works, but it's hard to use, especially on a phone:

- **The menu is one long wall.** It has 27 categories and about 250 dishes in a single scroll, with no search, filters or jump links.
- **The menu data contradicts itself.** Some items appear twice at different prices.
- **Key info is buried.** The phone number is only in the footer, nothing says whether it's open now, and the allergy notice has a typo ("Selfish" instead of "Shellfish").
- **It's heavy and cluttered.** A cookie wall covers the page on the first visit, it loads scripts it doesn't need, and the footer is stuffed with keywords for search engines.

The full write-up is in [docs/research.md](docs/research.md).

## What it will do

- [ ] A mobile-first home page with "Order online" and "Call" one tap away
- [ ] A live **Open now** badge that understands UK time and the midnight closing
- [ ] A menu built from one JSON file, so there's a single source of truth for every price
- [ ] A sticky category bar that highlights where you are as you scroll
- [ ] Search plus vegetarian and spice-level filters
- [ ] Clear delivery zones, allergy info, a map and directions
- [ ] Lighthouse scores of 90 or above for performance, accessibility, best practices and SEO

Progress is tracked in the [v1 launch milestone](https://github.com/Jack-Fox01/real-spice/milestone/1).

## Tech and decisions

| Choice | Why |
|---|---|
| Vanilla HTML, CSS and JS | Learn the fundamentals properly before reaching for tools that hide them. |
| No Tailwind (for now) | Tailwind is a shorthand for CSS. Learn the CSS first, then reconsider after v1. |
| Menu in `data/menu.json` | One source of truth: change a price once and it updates everywhere. |
| Prices stored in pence | Whole numbers avoid floating-point bugs (`0.1 + 0.2 !== 0.3`). |
| Keep the existing ordering system | Payments need a backend, payment security compliance and a merchant account. We improve browsing and hand off to the existing ordering system. |
| GitHub Pages | Free hosting that deploys on every push to `main`. |

## Run it locally

1. Clone the repo:
   ```bash
   git clone https://github.com/Jack-Fox01/real-spice.git
   ```
2. Go into the folder:
   ```bash
   cd real-spice
   ```
3. Open the folder in VS Code and click **Go Live** (needs the Live Server extension). Or start a local server instead:
   ```bash
   npx serve
   ```

> Opening `index.html` directly (a `file://` path) won't load the menu, because browsers block `fetch` from files. Use a local server.

## Project structure

```
index.html        home
menu.html         full menu with search and filters
contact.html      find us, delivery and allergy info
css/styles.css    design tokens and styles
js/               nav, menu, opening hours
data/menu.json    the menu: the single source of truth
images/           optimised WebP images
docs/             research, plan and wireframes
```

## Workflow

Each change comes from a [GitHub issue](https://github.com/Jack-Fox01/real-spice/issues):

1. Make a branch, for example `git switch -c 7-render-menu`.
2. Build it in small commits.
3. Open a pull request that says `Closes #7`, get it reviewed, then merge.

## Credits

- The menu, hours and contact details come from Real Spice's public website.
- Photos: credited here as they're added.
