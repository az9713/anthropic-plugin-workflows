# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A user-facing workflow guide and plugin reference for Anthropic's Claude plugin ecosystem. Organized by **what the user wants to accomplish** — not by repo or plugin. No build step, no dependencies, no server required — open `index.html` directly in a browser.

**GitHub:** https://github.com/az9713/anthropic-plugin-workflows  
**Live site:** https://az9713.github.io/anthropic-plugin-workflows/

## Files

| File | Purpose |
|------|---------|
| `index.html` | **Main app** — three-tab interface: "Plugin Overview" + "Skill Detail" + "Workflows" |
| `README.md` | Repo homepage summary (shown on GitHub) |
| `docs/README.md` | Full project documentation with workflow overview and image |
| `docs/sources.md` | Source repo URLs |
| `docs/finance_investment_workflows.jpg` | Screenshot used in docs |
| `.ignore/cc*.txt` | Session transcripts from the research agents that built this content |

## Three-Tab Interface

- **Plugin Overview** — card-per-plugin layout with personal-use highlights
- **Skill Detail** — searchable, collapsible per-skill reference (300+ skills across 5 repos)
- **Workflows** — cross-repo step-by-step workflows grouped by user goal (5 categories, 10 cards)

Tab switching via `switchTab(tab)` JS. Live search scoped to `#tab-skills`.

## Source Repositories

The five Anthropic repos this guide covers:
- `https://github.com/anthropics/knowledge-work-plugins` — 18 office-profession plugins
- `https://github.com/anthropics/claude-plugins-official` — 44 developer-focused plugins
- `https://github.com/anthropics/financial-services` — financial services agents and vertical plugins
- `https://github.com/anthropics/claude-plugins-community` — 600+ community plugins
- `https://github.com/anthropics/claude-for-legal` — legal-practice plugins

## HTML File Conventions

`index.html` is fully self-contained (no external dependencies, no CDN). It uses:
- Three-tab interface switched via `switchTab()` JS
- Dark theme via CSS custom properties on `:root`
- Collapsible plugin sections (`.plugin-toggle` / `.plugin-body` with `.open` class) in the Skills tab
- Live search bar in the Skills tab that filters plugins/skills and auto-expands matches
- Color coding by source repo (blue/purple/green/amber/red)
- Workflow cards use `.wf-card`, `.wf-step`, `.wf-badge` CSS classes with `wb-r1` through `wb-r5` repo color variants

When editing `index.html`, keep it self-contained — do not add external script or stylesheet links.

## Permissions

The `.claude/settings.local.json` allows fetching from `api.github.com` and `raw.githubusercontent.com`. Use these when re-researching or updating plugin content.
