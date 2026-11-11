# Research: the current Real Spice website

Reviewed on 11 November 2026: https://www.realspiceleven.co.uk/ (home) and /menu.

## What the site is

- A template site from an online-ordering platform (GloriaFood, which Oracle owns). The
  "See MENU & Order" buttons open the platform's ordering pop-up, which handles the basket,
  delivery/collection and payment.
- Pages: Home, Menu, Food Delivery, Contact Us. Each one repeats the same hero, the same
  "See MENU & Order" box and the same footer.

## Facts we must carry over

| Thing | Value |
|---|---|
| Name | Real Spice, Indian food in Leven |
| Address | 11 Shorehead, Leven KY8 4NR |
| Phone | 01333 422533 |
| Hours | Monday–Sunday, 16:00–00:00 (closes at midnight) |
| Service | Collection and delivery |
| Delivery | Zone 1: min £10, fee £2.50 · Zone 2: min £10, fee £3.00 · Zone 3: min £10, fee £7.00 |
| Allergens | Most dishes contain garlic, soya, gluten and sesame oil. Some contain milk, eggs, wheat, soybean, peanuts, tree nuts, fish and shellfish. Customers with allergies should phone before ordering. |
| Areas served | Leven, Methil, Methilhill, Buckhaven, Lundin Links, Lower/Upper Largo, Kennoway, Windygates, Cameron Bridge, East/West Wemyss, Markinch, Ladybank, Kingskettle and more |
| Menu | 27 categories, about 250 items, from Indian curries and tandoori to kebabs, pizza, burgers, set meals and "boxes" |

## Problems we're fixing

### Finding food is hard
1. **The menu is one long wall.** All 27 categories sit in a single scroll, with no jump
   links, no search and no filters. On a phone, getting to "Pizza" takes a lot of scrolling.
2. **The prices are confusing.** Most items say "From £x" but don't say what the options are
   (portion size? chicken or lamb?). Every price is also printed twice ("4.60" then "4.60 GBP"),
   so screen readers read it out twice.
3. **The data is inconsistent.** "Breads" repeats items from "Tandoori Nan Breads", and at
   least one price differs between the two (Garlic Paratha is £3.10 in one and £3.90 in the
   other). A rebuild with one source of truth (a JSON file) stops this happening.
4. **Dishes have no labels.** There are no vegetarian, spice-level or allergen markers on
   the dishes. The spice level is hidden in prose ("Madras: Hot").

### Trust and safety
5. **The allergy notice has errors.** It says "Selfish" where it means "Shellfish", and
   "Please be advice". On a safety notice that matters. It's also buried halfway down the page.
6. **The menu text has typos.** "DELCACIES", "Omlette", "Pilaue", "Sybees", "Fenugreek Lead",
   "Chansi" next to "Chasni", "Hoggie".
7. **The copy is generic filler.** "Brand New Online Ordering!!!" and "served like a king"
   say nothing about this restaurant.

### Basic info is hard to use
8. **The phone number isn't tappable** near the top of the page; it's only in the footer.
9. **Nothing says "Open now".** Customers have to work out from the hours whether it's open.
10. **The delivery zones are meaningless.** It lists Zone 1, 2 and 3 but never says which
    areas are in which zone.
11. **There's no map** or "Get directions" link for people collecting.

### Technical
12. **A full-screen cookie wall covers the page** on the first visit, before you see any food.
13. **It loads a lot of third-party scripts** (jQuery, a lightbox library, analytics beacons)
    for a page that is mostly text.
14. **The footer is stuffed with keywords:** 27 "Indian Food Delivery <town>" links. That's an
    old SEO trick that search engines now ignore or penalise.
15. **The hero repeats itself.** It shows the logo, "Real Spice" twice and the same order
    button twice above the fold.

## The key engineering decision: keep their ordering system

The ordering pop-up handles the basket, payments, delivery zones and sends orders to the
kitchen. **We are not rebuilding that.** Taking real payments needs a backend, PCI
compliance and the restaurant's merchant account, which is weeks of work and out of
scope for a week.

Instead, our site does the thing the current one does badly: it helps people **decide** what
to order quickly. Then it hands them to the existing ordering system with the same
order button (or a phone call). This is a normal, professional way to scope a project:
improve the part you own and connect to the parts you don't.

## Should we add Tailwind?

**Not for this project, at least not yet.** The aim this week is to learn CSS properly: layout
(flexbox and grid), the cascade, custom properties and responsive design. Tailwind is a
shorthand for CSS, and it pays off once you already know what it's short for. It would also
add a build step (Node and a CLI) to a project that otherwise needs nothing but a browser.
We'll look at it again after v1 ships.

## Images

Don't copy the photos from the current site; they belong to the platform's template. Use
photos the restaurant gives us, or free-licence stock (Unsplash or Pexels) as placeholders,
and give credit where the licence asks for it.
