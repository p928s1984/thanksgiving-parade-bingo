# Thanksgiving Parade Bingo Implementation Plan

> **For agentic workers:** Implement task-by-task. Steps use checkbox syntax.

**Goal:** Deliver one printable HTML file with 20 unique 5×5 parade bingo cards (10 balloons, 10 balloons+floats), Santa FREE center.

**Architecture:** Scrape/embed lineup image URLs into a self-contained HTML file with fixed-seed card generation and print CSS.

**Tech Stack:** Static HTML/CSS/JS (no build step)

## Global Constraints

- Single file: `thanksgiving-parade-bingo.html`
- 20 cards, letter print, image-only cells, Santa’s Sleigh FREE center
- Include Macy’s star/color balloons
- Images hotlinked from Macy’s lineup assets

---

### Task 1: Catalog images

- [ ] Extract balloon + balloonicle + float (+ stars) URLs from lineup page
- [ ] Reserve Santa’s Sleigh for center only

### Task 2: Build HTML

- [ ] Create `thanksgiving-parade-bingo.html` with embedded catalog, seeded shuffles, 20 pages, print styles

### Task 3: Verify

- [ ] Open in browser; confirm 20 pages, Santa center, both sets
