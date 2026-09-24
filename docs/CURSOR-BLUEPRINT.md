# CURSOR-BLUEPRINT — LinkLabz Master Prototype

> **PROTOTYPE sketch pad — NOT the canonical spec.** The canonical spec is the
> locked FINAL-MASTER one-pager (Trinity + Ravyn ACKed 2026-09-23; Cursor handoff
> in the bridge inbox). This doc records what this repo demos and how it differs
> from the Trinity reference build it was forked from.

## What this repo is

Private Trinity + Jon sandbox. Forked from `linklabz-trinity-preview` main
(@ `411a046`) on 2026-09-23. Purpose: let Jon poke at the locked future —
every FINAL-MASTER IN item working in one place — and iterate before Cursor
builds the real thing on Vader.

## Deltas vs the Trinity reference base

1. **Card overflow (⋯) menu** — new. Every review card gets a ⋯ button opening
   a menu: Favorite / Promote / Set lane (4 lanes inline) / Open link / Copy
   link. Closes on outside click or Escape. Honors the HOLD rule for lane and
   promotion changes.
2. **`localStorage` persistence** — new. Every mutation (`markDirty`) writes a
   snapshot to `linklabz-prototype-v1`; on load the snapshot restores reviews,
   bookmarks, spitballs, and to-dos — order, favorite flags, and promoted flags
   included. The manage bar now reads "Autosaves to this browser"; Download/Load
   JSON remains as the portable backup path.
3. **Phone bottom tab bar** — new. Fixed 6-button bar (Reviews / Saved / Ideas /
   To-do / Favs / Tools) shown only at ≤720px, 44px targets, safe-area padding.
   Reuses `showWorkspace`, so active states stay in sync with the top tabs.
4. **Card Swap placement** — the `card-concepts/index.html` test is linked from
   the Tools tab panel and from the ⌘K command palette ("Open Card Swap").
   Nowhere else. Per the lock: Tools + command palette + search only.

Everything else (facets, combobox, stat pills, drawer, workspace menu, seed
data) is inherited unchanged from the Trinity reference.

## Data model + persistence keys

- In-page seed arrays: `reviews`, `bookmarks`, `spitballs`, `todos`
  (frozen `seededReviews` kept for the protected-seed check).
- Autosave key: `localStorage["linklabz-prototype-v1"]` →
  `{ v: 1, savedAt, reviews, bookmarks, spitballs, todos }`.
- The real Cursor build must persist the same surface (Promoted / Favorites /
  queue order) — this prototype is the behavioral reference.

## Real vs stubbed

- Real: all 9 FINAL-MASTER IN items, full dataset, autosave, filters, drawer,
  command palette, workspace Download/Load.
- Stubbed / out of scope: multi-user sync, server backend, the Help lightbox
  (wave 2 per the lock).

## Wiring checklist (for Cursor's real build)

- [ ] Persist Promoted / Favorites / queue order (not session-only)
- [ ] Card overflow menu on cards (Favorite, Promote, Set lane, Open, Copy link)
- [ ] Phone bottom tab bar (36–44px targets)
- [ ] Card Swap under Tools + command palette + search ONLY
- [ ] Rectangular facet chips with counts
- [ ] Zero data loss from the master board

## Changelog

- **2026-09-23** — Repo created from Trinity reference @ `411a046`. Added: card
  overflow menu, `localStorage` autosave, phone bottom tab bar, Card Swap Tools
  placement, PROTOTYPE badge, og meta, dark README hero (Playwright,
  colorScheme dark, 1440×900). Verified: 19/7/6/2 dataset, persistence across
  reload, mobile tab bar, no JS errors.
