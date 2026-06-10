# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
bundle install                              # Install Ruby dependencies
bundle exec jekyll serve --livereload       # Serve locally with live reload
bundle exec jekyll build                    # Build static site to _site/
```

Local site runs at `http://127.0.0.1:4000/MoSAIC-P38/`.

## Architecture

This is a **Jekyll 4.3 static documentation site** for the MoSAIC P-38 hardware architecture project at Lawrence Berkeley National Laboratory (LBNL).

- **Theme:** [`chrisrhymes/bulma-clean-theme@v0.14.0`](https://github.com/chrisrhymes/bulma-clean-theme) loaded as a remote Jekyll theme. Theme components come from GitHub at build time — override any theme file by creating the same path locally.
- **Styling:** `assets/css/app.scss` applies LBNL Visual Identity colors over Bulma. The canonical palette: Dark Blue `#00313C`, Teal `#007681`, Light Gray `#B1B3B3`, Dark Gray `#63666A`, Bright Green `#84BD00`.
- **Head overrides:** `_includes/head.html` injects Bulma CSS (CDN), Alpine.js, Font Awesome, js-cookie, and Google Analytics hooks ahead of the theme's head.
- **Navigation:** Defined in `_data/navigation.yml`. All links must include the `/MoSAIC-P38/` baseurl prefix.
- **Content pages:** Each top-level `.md` file (`index.md`, `architecture.md`, `getting-started.md`, `docs.md`, `team.md`) becomes a route. Front matter controls layout, title, and sidebar visibility.
- **Deployed at:** `https://lbnlcomputerarch.github.io/MoSAIC-P38` via GitHub Pages.

## Key Configuration

`_config.yml` sets `baseurl: "/MoSAIC-P38"` — all internal links and assets must be prefixed with `{{ site.baseurl }}` in templates.
