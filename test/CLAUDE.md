# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

A static self-introduction web page split into `index.html` (markup) and `style.css` (styles). There is no build tooling, package manager, linter, or test suite, and no JavaScript.

## Commands

- **Preview**: open the file directly in a browser, e.g. `open index.html` (macOS).
- There is no build, lint, or test command — changes take effect immediately on save/reload.

## Architecture

HTML and CSS are kept in separate files (`index.html`, `style.css`); add a `script.js` only if/when JS is actually introduced, and link it the same way rather than inlining `<script>`/`<style>` back into `index.html`.

`index.html` is structured as a vertically stacked sequence of full-width panels inside a single `.sheet` container (max-width 480px, centered), styled to resemble a printed leaflet/flyer rather than a conventional card-based portfolio page. The sections, in order, are:

1. **표지 (Cover)** — `.hero`: colored background with decorative overlapping circle "dots", name wordmark, subtitle, and an icon row.
2. **글 소개 (Written intro)** — `.write`: short bio paragraph.
3. **기타 소개 (Other info)** — `.etc`: labeled list of ID/school/email-style facts.
4. **관심 분야 (Interests)** — `.interests`: pill/chip tags.

Each section owns its own color and shares a `.kicker` label style for the small caps section title. When redesigning or restyling, prefer adjusting the CSS custom properties in `:root` (`--pink`, `--pink-dot`, `--blue`, `--ink`, `--white`) over hardcoding new colors, and keep the leaflet-style panel structure (edge-to-edge stacked blocks, no card shadows/gaps) unless asked to change the overall layout concept.
