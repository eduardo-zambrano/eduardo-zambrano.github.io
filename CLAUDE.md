# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML5 academic portfolio website for Professor Eduardo Zambrano, hosted on GitHub Pages at eduardo-zambrano.github.io. Built on the "Air" Bootstrap template from FreeHTML5.co.

## Deployment

The site deploys automatically to GitHub Pages when pushed to the `main` branch. No build process required.

Many unrelated files show as modified in the working tree (file-permission changes only, from Dropbox), so stage only the files you changed rather than `git add .`:

```bash
git add <changed files>
git commit -m "message"
git push origin main
```

## Architecture

**Static site with no build tools** - HTML/CSS/JS served directly.

### Pages
- `index.html` - Homepage with bio, contact info, research interests
- `research.html` - Published papers with descriptions and links
- `teaching.html` - Archived teaching effectiveness research
- `links.html` - Personal interests

### Styling
- SASS source in `sass/` compiles to `css/style.css` (pre-compiled, no rebuild needed for most changes)
- Primary colors: pink/red (#DD356E), yellow (#FEE856)
- Bootstrap 3 grid system for responsive layout

### JavaScript
- `js/main.js` - Custom initialization (mobile menu, animations, scroll triggers)
- Dependencies: jQuery, Bootstrap 3 JS, Waypoints, Flexslider, Magnific Popup

### Assets
- `documents/` - Academic papers (PDFs), CV
- `photos/` - Personal images (homepage portrait: `photos/eduardo-2026.jpg`, credited on the page to Victor Andrés Zambrano)
- `images/` - Template/design images
- `fonts/` - Icomoon icons + Bootstrap Glyphicons

## Editing Content

Most updates involve editing HTML directly:
- Add papers: Edit `research.html`. Each working paper is one `<p>` (title linking to a Dropbox-hosted PDF, date, abstract, and often a "(Lean files)" link to a GitHub repo under `eduardo-zambrano/`), followed by an `&nbsp;` spacer paragraph
- Remove papers: delete the paper's `<p>` together with the spacer that follows it. The linked GitHub repo and Dropbox share link stay public unless changed separately
- Update CV: Replace `documents/zambrano.pdf`
- Change bio: Edit `index.html`
- Change homepage photo: resize (don't crop) into `photos/`, update the `<img>` near the top of `index.html`, and keep the photo-credit line beneath it

Navigation is duplicated in each HTML file's `<nav>` section.
