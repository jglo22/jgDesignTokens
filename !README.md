# globalDesignTokens — Rehydration

status: active

**GitHub Issues:** Open tasks tracked in [Project #1](https://github.com/users/jglo22/projects/1) — filter by Feature: `globalDesignTokens`

## What this is

W3C DTCG format design tokens defining Jim's visual identity. Token files + use-case stylesheets live in the public repo [`jgTokensAndStylesheets`](https://github.com/jglo22/jgTokensAndStylesheets). This lifeOS folder is context/docs only — no token files here.

## Current state

Tokens-only repo. `tokens.css` renamed to `variables.css`. Use-case CSS files (e.g. `cv.css`) moved out — they now live alongside their consumers (e.g. `lifeOS/features/cvBuilder/`). `sample.html` visual preview remains here. `variables.css` is duplicated into each consumer repo at build time.

## Decisions made

1. **W3C DTCG format** — industry standard, tool-agnostic
2. **Split token files** — organised by category (color, typography, spacing, border, page)
3. **Tokens-only public repo** (`jgTokensAndStylesheets`) — use-case CSS files live with their consumers, not here
4. **Token units stored as px** — CSS files handle any conversion needed per medium
5. **No context mapping** — no `print.json` / `digital.json`; per-medium decisions handled in each consumer's CSS
6. **`variables.css` duplicated per consumer** — local copy used at build time; updated manually when tokens change
7. **`tokens.css` renamed to `variables.css`** — clearer name, less confusion with JSON token files

## What consumes these tokens

| Consumer | Where | How |
|----------|-------|-----|
| CV builder | `lifeOS/features/cvBuilder/variables.css` (local duplicate) | Copied from here when tokens change |
| sample.html | Public repo | Token values embedded directly for browser preview |
| Figma (future) | `tokens.json` via GitHub | Tokens Studio plugin |
| Website (future) | `tokens.json` via GitHub | Fetched as raw URL |

## To investigate

- Combine Figma files with design tokens? How to extract them from Figma — 2026-02-05

## Updates

- 2026-03-02 by Claude (Sonnet 4.6) [desktop] — renamed tokens.css → variables.css, moved cv.css and sampleCV/ to cvBuilder, repo is now tokens-only
- 2026-02-18 by Claude (Sonnet 4.6) [desktop] — merged CLAUDE.md into README, deleted stale token files from lifeOS, pushed sample.html to public repo, simplified architecture: px tokens, use-case CSS files, no context mapping
- 2026-02-11 by Claude (Opus 4.6) [laptop] — designed contextual token mapping (now removed)
