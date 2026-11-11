<div align="center">

# 🌶️ Real Spice
 
**A faster, friendlier website for Real Spice, an Indian takeaway in Leven, Fife.**
 
Plain HTML, CSS and JavaScript. No framework, no build step.
 
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](#-tech-and-decisions)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](#-tech-and-decisions)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](#-tech-and-decisions)
[![GitHub Pages](https://img.shields.io/badge/hosted%20on-GitHub%20Pages-222?logo=github)](https://jack-fox01.github.io/real-spice/)
[![Status](https://img.shields.io/badge/status-in%20progress-orange)](https://github.com/Jack-Fox01/real-spice/milestone/1)
 
[**🌐 Live site**](https://jack-fox01.github.io/real-spice/) ·
[**📋 Roadmap**](https://github.com/Jack-Fox01/real-spice/milestone/1) ·
[**🐛 Issues**](https://github.com/Jack-Fox01/real-spice/issues) ·
[**🔍 Research**](docs/research.md)
 
</div>

> [!IMPORTANT]
> **This is an unofficial concept**, built as a learning and portfolio project. It is not the restaurant's official site.
> To order for real, visit **[realspiceleven.co.uk](https://www.realspiceleven.co.uk/)** or call **📞 01333 422533**.
 
> [!NOTE]
> The live site goes up once GitHub Pages is turned on in [#1](https://github.com/Jack-Fox01/real-spice/issues/1).
 
---
 
## 📑 Contents
 
- [The problem](#-the-problem)
- [What it will do](#-what-it-will-do)
- [Tech and decisions](#-tech-and-decisions)
- [Run it locally](#-run-it-locally)
- [Project structure](#-project-structure)
- [Workflow](#-workflow)
- [Credits](#-credits)

---
 
## 🤔 The problem
 
The [current site](https://www.realspiceleven.co.uk/) works, but it's hard to use, especially on a phone.
 
| | Issue | Details |
|:-:|---|---|
| 📜 | **The menu is one long wall** | 27 categories and about 250 dishes in a single scroll, with no search, filters or jump links. |
| ⚠️ | **The menu data contradicts itself** | Some items appear twice at different prices. |
| 🔎 | **Key info is buried** | The phone number is only in the footer, nothing says whether it's open now, and the allergy notice has a typo ("Selfish" instead of "Shellfish"). |
| 🐢 | **It's heavy and cluttered** | A cookie wall covers the page on first visit, it loads scripts it doesn't need, and the footer is stuffed with SEO keywords. |
 
📖 Read the full write-up in [`docs/research.md`](docs/research.md).
 
---
 
## ✨ What it will do
 
- [ ] 📱 A mobile-first home page with **Order online** and **Call** one tap away
- [ ] 🟢 A live **Open now** badge that understands UK time and the midnight closing
- [ ] 🗂️ A menu built from one JSON file, so every price has a single source of truth
- [ ] 📌 A sticky category bar that highlights where you are as you scroll
- [ ] 🔍 Search, plus vegetarian and spice-level filters
- [ ] 🗺️ Clear delivery zones, allergy info, a map and directions
- [ ] 💯 Lighthouse scores of **90+** for performance, accessibility, best practices and SEO

Progress is tracked in the [**v1 launch milestone**](https://github.com/Jack-Fox01/real-spice/milestone/1).
 
---
 
## 🛠️ Tech and decisions
 
| Choice | Why |
|---|---|
| **Vanilla HTML, CSS and JS** | Learn the fundamentals properly before reaching for tools that hide them. |
| **No Tailwind (for now)** | Tailwind is a shorthand for CSS. Learn the CSS first, then reconsider after v1. |
| **Menu in `data/menu.json`** | One source of truth: change a price once and it updates everywhere. |
| **Prices stored in pence** | Whole numbers avoid floating-point bugs (`0.1 + 0.2 !== 0.3`). |
| **Keep the existing ordering system** | Payments need a backend, payment security compliance and a merchant account. This site improves browsing and hands off to the existing ordering system. |
| **GitHub Pages** | Free hosting that deploys on every push to `main`. |
 
---
 
## 🚀 Run it locally
 
**1. Clone the repo**
 
```bash
git clone https://github.com/Jack-Fox01/real-spice.git
```
 
**2. Go into the folder**
 
```bash
cd real-spice
```
 
**3. Start a local server**
 
- **VS Code:** open the folder and click **Go Live** (needs the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension), **or**
- **Terminal:**
```bash
  npx serve
```
 
> [!WARNING]
> Opening `index.html` directly (a `file://` path) **won't load the menu**, because browsers block `fetch` from local files. Always use a local server.
 
---
 
## 📁 Project structure
 
```text
real-spice/
├── index.html        # Home
├── menu.html         # Full menu with search and filters
├── contact.html      # Find us, delivery and allergy info
├── css/
│   └── styles.css    # Design tokens and styles
├── js/               # Nav, menu, opening hours
├── data/
│   └── menu.json     # The menu: the single source of truth
├── images/           # Optimised WebP images
└── docs/             # Research, plan and wireframes
```
 
---
 
## 🔄 Workflow
 
Every change starts from a [GitHub issue](https://github.com/Jack-Fox01/real-spice/issues).
 
```mermaid
flowchart LR
    A[📝 Issue] --> B[🌿 Branch]
    B --> C[💾 Small commits]
    C --> D[🔀 Pull request]
    D --> E[👀 Review]
    E --> F[✅ Merge]
```
 
<details>
<summary><b>Step-by-step example</b></summary>

1. Make a branch named after the issue:
```bash
   git switch -c 7-render-menu
```
2. Build it in small, focused commits.
3. Open a pull request with `Closes #7` in the description, get it reviewed, then merge.

</details>

---
 
## 🙏 Credits
 
- The menu, hours and contact details come from Real Spice's public website.
- 📷 Photos will be credited here as they're added.

<div align="center">

<sub>Made with ☕ and 🍛 in Fife</sub>
 
</div>
