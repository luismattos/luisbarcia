# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website/blog built with Hugo using the PaperMod theme (included as a git submodule).

## Common Commands

```bash
# Start development server
hugo server

# Start with drafts enabled
hugo server -D

# Build the site (outputs to public/)
hugo

# Create new content
hugo new content/<section>/<filename>.md
```

## Architecture

- **Theme**: PaperMod (git submodule at `themes/PaperMod`) - **NEVER modify theme files directly**
- **Config**: `hugo.yaml` - site configuration, menus, params, social links
- **Content**: Flat structure in `content/` - pages are markdown files with front matter
- **Static**: `static/` - favicons and logo
- **Search**: Enabled via JSON output and Fuse.js (configured in `hugo.yaml` under `fuseOpts`)

## Content Structure

Pages use Hugo front matter. The `content/post.md` maps to `/archives/` for blog posts. Search requires `layout: "search"` in front matter.

## Customization (without modifying theme)

To customize appearance or behavior, use Hugo's override system:
- `layouts/` - override theme templates
- `assets/css/` - custom CSS
- `hugo.yaml` - theme parameters and configuration

## Key Configuration Notes

- Base URL currently set to localhost (change for production deployment)
- JSON output enabled for search functionality
- Default archetype creates draft posts with auto-generated titles from filename
