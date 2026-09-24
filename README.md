# ⚡ LinkLabz — Master Prototype

> Trinity + Jon's private sandbox: the locked **FINAL-MASTER** spec as a working prototype — a glance into the future before Cursor builds the real thing. Sketch pad, not source of truth.

[![GitHub Pages](https://img.shields.io/github/deployments/jonbeatz/linklabz-master-prototype?label=github%20pages)](https://jonbeatz.github.io/linklabz-master-prototype/)
[![Last commit](https://img.shields.io/github/last-commit/jonbeatz/linklabz-master-prototype)](https://github.com/jonbeatz/linklabz-master-prototype/commits/main)
[![Repo size](https://img.shields.io/github/repo-size/jonbeatz/linklabz-master-prototype)](https://github.com/jonbeatz/linklabz-master-prototype)
![Static site](https://img.shields.io/badge/site-static%20html-blue)

**🚀 Live preview:** https://jonbeatz.github.io/linklabz-master-prototype/

![LinkLabz master prototype](assets/screenshot.png?v=1)

## What's inside

Everything from the locked FINAL-MASTER one-pager (2026-09-23), working:

- **Card overflow (⋯) menu** — Favorite, Promote, Set lane, Open, Copy link on every review card. *New in this prototype.*
- **Persistent state** — Promoted, Favorites, and queue order autosave to `localStorage` and survive a full reload. This is the key data rule the real Cursor build must implement — demo it here. *New in this prototype.*
- **Phone bottom tab bar** — 6-section tab bar on ≤720px screens, 44px touch targets. *New in this prototype.*
- **Card Swap under Tools only** — the layout concept test lives in the Tools tab + command palette + search. Not an island, not the top bar. *New in this prototype.*
- **Faceted filter bar** — rectangular chips with counts; Promoted/Favorites filters; 36–44px targets.
- **Searchable project combobox** — multi-select popover with removable chips.
- **Drag-reorder to-dos** — Up/Down buttons as the keyboard fallback; order persists.
- **Workspace menu** — Download / Load workspace JSON (portable backup alongside autosave).
- **Live stat pills** — review totals update with every change.
- **Full dataset preserved** — 19 reviews, 7 bookmarks, 6 spitballs, 2 to-dos, 5 favorites, 12 gradients, 2 tools.

Deliberately **cut** (per the lock): gold foil cards, Coast/Band/Cover as defaults, gold top-bar Card Swap button, lab-toggle chrome, redundant glass/goo, monograms.

## Tech stack

| Layer   | Choice                                                        |
| ------- | ------------------------------------------------------------- |
| Markup  | Single self-contained `index.html` (CSS + JS inlined)         |
| Runtime | None — opens straight in the browser, no build step           |
| Hosting | GitHub Pages, served from `main` (`.nojekyll`, no Jekyll pass)|
| Data    | JSON seeded in-page; autosaved to `localStorage` (`linklabz-prototype-v1`) |
| Lanes   | Reviews / Bookmarks / Spitballs / To-do / Favorites / Gradients / Tools |

## Project structure

```text
linklabz-master-prototype/
├── index.html          # the whole app — self-contained build
├── assets/
│   └── screenshot.png  # README hero shot (dark)
├── brand/              # shared LinkLabz logo/brand pack
├── card-concepts/
│   └── index.html      # Card Swap concept test (Tools only)
├── docs/
│   └── CURSOR-BLUEPRINT.md  # prototype notes + changelog (NOT the canonical spec)
├── .nojekyll           # tell Pages to serve files as-is
└── README.md
```

## Workflow — branches, not overwrites

`main` always mirrors the latest approved build. Every change gets cut as a **new branch** off `main`. Nothing is silently replaced. No PRs unless Jon asks.

**This repo is a sketch pad.** The canonical spec is the locked FINAL-MASTER one-pager (Trinity + Ravyn ACKed 2026-09-23). Tweaks made here do **not** flow to Cursor's real build on their own — they go back through Trinity as an amendment to the locked handoff.

## Use this repo as a template

This README is the house pattern for Jon's preview repos. Copy the shape:

1. Title + one-line description of whose build it is and what changed.
2. Badge row: Pages deploy status, last commit, repo size, site type.
3. Live preview link, then a real screenshot (`assets/screenshot.png`).
4. "What's inside" — the feature list in plain language.
5. "Tech stack" — the table above; keep it honest and short.
6. "Project structure" — the tree, so the next person knows where things live.
7. "Workflow" — the branching rule, so `main` never gets quietly overwritten.
