# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a **single-page static HTML website** for the Association Nationale de Classe First Class 8 (a French sailing class association). The entire site lives in one file: `index.html`. There is no build system, no package manager, no preprocessor, and no test suite.

## Development

Open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

Deployment is via GitHub Pages — pushing to `main` publishes automatically.

## Architecture

Everything is in `index.html`:

- **CSS** — all styles are in a single `<style>` block in `<head>`. A CSS custom property system defines the color palette (blues, reds, grays) and spacing at the top under `:root`.
- **HTML** — one long document with anchor-linked sections (`#calendrier`, `#presentation`, `#jauge`, `#staff`, `#docs`). Navigation links scroll to these anchors.
- **JavaScript** — any scripts are inline at the bottom of `<body>`.

Assets alongside `index.html`:
- `fc8-logo.svg` — SVG logo
- `class8.jpg` — boat photo
- `profil.jpg` — profile photo

## Content language

All content is in **French**. Keep any new text in French.

## CSS conventions

- Utility-first inline CSS with BEM-like class names (e.g., `.news-card`, `.cal-item`, `.sb-head`)
- Color variables: `--blue`, `--blue2`, `--blue-lt`, `--red`, `--red-lt`, `--white`, `--gray-bg`, etc.
- Max content width: `1180px`, centered with `margin: 0 auto`
- Responsive breakpoints are handled with `@media` queries inside the same `<style>` block
