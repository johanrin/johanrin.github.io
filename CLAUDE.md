# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static blog site deployed to GitHub Pages. The site focuses on AI, cloud architecture, and Microsoft Foundry content.

**Tech Stack:** Hugo (v0.153.2) with hugo-blog-awesome theme (Git submodule)

## Common Commands

```bash
# Local development
hugo server                         # Start dev server with live reload

# Production build
hugo --gc --minify                  # Build with garbage collection and minification

# Create new blog post
hugo new posts/my-post/index.md     # Creates post from archetypes/default.md template
```

## Architecture

```
content/
├── posts/          # Blog posts (each post is a directory with index.md + images)
├── pages/          # Static pages (about.md)
└── _index.md       # Homepage

layouts/            # Custom overrides for theme templates
├── _default/_markup/render-image.html  # Image zoom effect
├── partials/bio.html                   # Author bio
├── partials/custom-head.html           # OG/Twitter meta tags
└── robots.txt                          # SEO configuration

themes/hugo-blog-awesome/   # Theme submodule (do not edit directly)
```

## Content Structure

Blog posts use directory-based organization:
```
content/posts/my-post/
├── index.md        # Post content with YAML front matter
├── cover.png       # Featured image
└── *.png           # Additional images
```

**Front matter fields:** title, date, image, description, categories, tags, draft

## Configuration

Main configuration is in `hugo.toml`:
- Language: English (en-us)
- Theme: hugo-blog-awesome
- Dark mode by default
- Google Analytics enabled
- Table of Contents: H2-H4 levels

## Deployment

GitHub Actions workflow (`.github/workflows/hugo.yaml`) automatically builds and deploys to GitHub Pages on push to `main` branch.
