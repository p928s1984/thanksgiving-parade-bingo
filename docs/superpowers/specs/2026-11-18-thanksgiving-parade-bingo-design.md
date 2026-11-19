# Thanksgiving Day Parade Bingo — Design

**Date:** 2026-11-18  
**Status:** Approved for planning  
**Deliverable:** Single printable HTML file

## Goal

Create 20 unique, printable Thanksgiving Day Parade bingo cards using official images from the [Macy’s 2026 Parade Lineup](https://www.macys.com/s/parade/lineup/), for family TV watching. Image-only squares help kids learn shapes and colors (including similar Macy’s star balloons).

## Requirements

| Requirement | Decision |
|---|---|
| Format | Printable HTML (open in browser → Print) |
| Card count | 20 total: 10 balloons-only + 10 balloons+floats |
| Grid | 5×5 |
| Center square | Santa’s Sleigh image + small FREE badge (same on every card) |
| Labels | Image only (no names under squares) |
| Randomization | Unique shuffle per card; fixed so reprints match |
| Star balloons | **Include** near-identical Macy’s color/star balloons (learning shapes/colors) |

## File layout

- Project folder: `Documents/thanksgiving-parade-bingo/`
- Main deliverable: `thanksgiving-parade-bingo.html`
- Spec: this document

One HTML file contains all 20 cards. Each card is one letter-size printed page (`page-break-after`).

## Card sets

### Set A — Balloons (cards 1–10)

Pool includes:

- Giant balloons
- Featured balloons
- Novelty balloons (including Macy’s star / color variants)
- Balloonicles

Exclude: floats, clowns, bands, performers, specialty units.

Santa’s Sleigh is **not** in the random pool (reserved for center).

### Set B — Balloons + floats (cards 11–20)

Pool = Set A pool + float thumbnails from the lineup page.

Same Santa center rule.

## Board generation

1. Scrape/collect `{ name, imageUrl, category }` entries from the lineup page (or embed a curated list derived from it).
2. Build two pools as above; remove Santa’s Sleigh from both pools.
3. For each card: shuffle the pool with a fixed seed (or precomputed shuffle), take 24 images, place into the 24 non-center cells.
4. No duplicate image on the same card.
5. Across cards, repetition of popular balloons is allowed (expected with limited pool).

## Page layout (print)

Each page:

1. Title: “Thanksgiving Day Parade Bingo”
2. Subtitle: set label + card number (e.g. “Balloons · Card 3” / “Balloons & Floats · Card 12”)
3. 5×5 CSS grid of square cells
4. Optional footer tip: “Mark a square when you see it on the parade!”

Print CSS:

- `@page { size: letter; margin: 0.4in; }`
- One card per page
- Cream background; ink-friendly borders

## Visual design

- Palette: cranberry red (`#8B1E3F`), forest green (`#2F5D3A`), cream (`#F7F1E6`), near-black text/borders
- Title: expressive serif; meta line: simple sans
- Cells: thin dark border; `object-fit: cover` images filling the square
- Center: Santa’s Sleigh + compact FREE badge (e.g. corner ribbon or small centered pill) so free space is obvious without a text-heavy square
- No decorative card chrome, stats, or secondary marketing blocks — one job per page

## Image sourcing

- Use official thumbnail URLs from Macy’s/Contentful lineup assets (e.g. `storage.googleapis.com/contentful-media-uploads/parade/2026/page-lineup/...`)
- Hotlink in the HTML for simplicity
- Document that an internet connection is needed when opening/printing so images load
- Attribution footer (small, print-safe): “Images from Macy’s Thanksgiving Day Parade lineup — for personal use”

## Non-goals

- Digital tap-to-mark play mode
- PDF generation tooling
- Caller/master board (can be added later if requested)
- Offline image bundling (unless printing fails without it)

## Success criteria

- Opening the HTML and printing yields 20 distinct letter pages
- Cards 1–10 use only balloon-type images; 11–20 include floats
- Every card has Santa’s Sleigh FREE in the center
- Macy’s star/color balloons appear in the pools
- Squares are image-only aside from the FREE badge
- Reopening the file produces the same card layouts
