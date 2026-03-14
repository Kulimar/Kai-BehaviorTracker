# Task List

## Current Sprint

_No active tasks._

---

## Backlog

- Set up Firebase project for cross-device data sync
- Wire up sound effects from `sfx/` to polite/rude actions
- Daily/weekly summary reports
- Trend tracking over longer periods
- Reward system for hitting polite streaks
- Multi-child support

---

## Completed

### Charts / Analytics Tab (2026-03-13)
- [x] Added Chart.js CDN and tab navigation (Tracker | Charts)
- [x] Built daily stacked bar chart (green polite / red rude per day)
- [x] Date filters: Last 7 Days, Last 30 Days, This Month, This Year, Custom
- [x] Averages view: 7-day rolling average line chart
- [x] Standout days: auto-detect outlier days, highlight in chart + card list
- [x] Summary stats: total polite/rude, avg/day, best day

### localStorage Persistence (2026-03-13)
- [x] Data persists across page reloads and app restarts
- [x] Loads from localStorage on init, saves after every mutation
- [x] Works on mobile browsers via GitHub Pages

### Project Scaffold (2026-03-13)
- [x] Created CLAUDE.md, tasks, agents, project context
- [x] Initialized git repo, pushed to GitHub
- [x] Set up GitHub Pages on gh-pages branch

---

## Session Summary (2026-03-13)

**What was done:**
- Scaffolded full dev harness (CLAUDE.md, tasks, agents, project context)
- Created GitHub repo (Kulimar/Kai-BehaviorTracker) and pushed
- Set up GitHub Pages: https://kulimar.github.io/Kai-BehaviorTracker/
- Built Charts tab with 3 views: Daily stacked bars, Rolling averages, Standout days
- Added localStorage persistence so data survives reloads on mobile

**What's next:**
- Firebase setup for cross-device sync (on hold per user)
- Sound effects integration
- Reward/streak system

**Blockers:** None

---

## Review Notes

_Post-implementation review observations go here._
