# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static site comparing 20 men's multivitamins, hosted on GitHub Pages at `ariel-frischer.github.io/multivitamin-compare/`. The entire site is a single `index.html` file with inline CSS and a hand-coded HTML table — no build tools, no JS frameworks, no dependencies.

## Architecture

- **`index.html`** — the entire app: CSS variables for dark theme, responsive styles, a large `<table>` with nutrient data, color-coded cells (`.g`/`.y`/`.r` classes for green/yellow/red based on %DV), bioavailability form tags (`.form-methyl`, `.form-active`, `.form-chelated`, `.form-synthetic`), and tier badges (`.tier-1` through `.tier-5`).
- **`README.md`** — article-length writeup with scoring rubric, tier rankings, and supplement stack recommendations. Serves as both the repo README and the companion article.

## Key Conventions

- Products are ranked in columns; nutrients are rows grouped by section headers (`.section-header`).
- First column is sticky (product names stay visible on horizontal scroll). Header row is also sticky.
- Cell tooltips use `data-tip` attribute with CSS `::after` pseudo-element (no JS).
- Color coding: `.g` = ≥100% DV, `.y` = 50-99% DV, `.r` = <50% or missing, `.n` = not applicable.
- Mobile breakpoint at 768px reduces font sizes and padding.

## Development

No build step. Open `index.html` in a browser or use any static server:

```bash
python3 -m http.server 8000
```
