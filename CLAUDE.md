# Mini Retirement Planner — Project Notes for AI Assistants

## Overview

Single-file interactive financial planning tool. The entire app lives in `index.html` — no build step, no framework, no backend. The only external dependency is Chart.js (loaded from CDN).

## Canonical Definitions

These definitions are the ground truth for how terms are used throughout the tool, its copy, tooltips, and tutorials. Use them consistently in any future changes.

**Retirement**
The point after which the user plans to have no (or little) outside income beyond the appreciation of their investments. This is NOT simply "stopping work" — it is specifically defined by the absence of outside earned income.

**Mini Retirement**
A defined span of time during which the user similarly has no (or little) outside income beyond investment appreciation, before eventually returning to work. It is a temporary career break, not permanent retirement.

## Core Simulation Assumptions

| Parameter | Value | Notes |
|---|---|---|
| Annual investment growth | 7% | Applied every year regardless of phase |
| Safe withdrawal rate | 4% | Used to derive FIRE number and retirement withdrawals |
| Life expectancy target | Age 100 | Simulation runs to age 100 |
| Mini retirement income | None | Portfolio draws down; no contributions |
| FIRE number formula | Annual retirement spend ÷ 0.04 | Based on the "4% rule" |

## Architecture

- **Single file:** `index.html` contains all HTML, CSS, and JS
- **No build step:** Open directly in any browser
- **State:** Held in memory (`miniRets` array, form inputs); persisted to `localStorage` under `miniRetPlanner_v1`
- **Chart:** Chart.js 4.4.1 via CDN
- **Fonts:** DM Sans (body), DM Mono (monospace/labels) via Google Fonts

## Key JS Functions

| Function | Purpose |
|---|---|
| `recalc()` | Master update — reads all inputs, runs simulation, updates UI. Call after any state change. |
| `simulate()` | Core year-by-year portfolio simulation |
| `renderChart()` | Rebuilds Chart.js instance |
| `renderTimeline()` | Rebuilds the life-phase timeline bar |
| `renderMiniRets()` | Re-renders all mini-retirement cards from `miniRets` array |
| `addMiniRet()` / `removeMiniRet()` | Mutate `miniRets` array, then call `renderMiniRets()` and `recalc()` |

## localStorage Keys

| Key | Purpose |
|---|---|
| `miniRetPlanner_v1` | Persisted input state (JSON) |
| `miniRetPlanner_tutorial_seen` | Set to `'true'` after the user dismisses the tutorial once |

## CSS Design Tokens

All colours and surfaces are CSS variables defined on `:root`. Always use variables, never hardcode hex values in new CSS. Key tokens: `--bg`, `--surface`, `--surface2`, `--border`, `--border2`, `--text`, `--text-muted`, `--text-dim`, `--accent`, `--accent-dim`, `--accent-glow`, `--danger`, `--warn`, `--blue`, `--purple`.
