# Project Context

## Project Name
Kai's Behavior Tracker

## Overview
A Duolingo-inspired web app for tracking a child's (Kai's) polite vs rude behavioral choices throughout the day. Designed for parents/caregivers to log incidents with optional context notes, view history, and export/import data. Features sound feedback, animated UI, and Firebase-backed cloud persistence.

## Tech Stack
- **Frontend:** HTML5, Vanilla JavaScript (ES modules), CSS (Tailwind CDN)
- **Backend/DB:** Firebase (Anonymous Auth + Firestore real-time sync)
- **Icons:** Font Awesome 6.4 (CDN)
- **Fonts:** Google Fonts (Nunito)
- **Audio:** MP3 sound effects for behavior feedback
- **Hosting:** Static file serving (no build step required)

## Architecture Notes
- Single-file architecture: all app logic lives in `index.html`
- Firebase config is injected via global variables (`__firebase_config`, `__app_id`, `__initial_auth_token`)
- Falls back to local in-memory mode when no Firebase config is present
- Firestore path: `artifacts/{appId}/users/{userId}/behavior_logs`
- Real-time listener via `onSnapshot` keeps UI in sync across devices
- All sorting done client-side (no complex Firestore queries)

## Current State
- Core app is functional: polite/rude counters, note input, history timeline, delete entries
- Export/import JSON functionality works
- Sound effects are present in `sfx/` but not yet wired into the UI
- Chart style reference image exists (`ChartStyleExample.png`) suggesting planned data visualization

## Goals
- **Short-term:** Wire up sound effects, add data visualization/charts, polish mobile UX
- **Long-term:** Daily/weekly summaries, trend tracking, reward system, multi-child support

## Key Files & Directories
```
BehaviorTracker/
  index.html            # The entire application
  ChartStyleExample.png # Reference for planned chart UI
  sfx/                  # Sound effect MP3s
    Positive1-4.mp3     # Polite behavior sounds
    Positive_jig.mp3    # Polite celebration sound
    Rude1-4.mp3         # Rude behavior sounds (note: rude2.mp3 lowercase)
    Rude_jig.mp3        # Rude alert sound
```

## External Dependencies
- Firebase JS SDK v11.6.1 (loaded via CDN)
- Tailwind CSS (loaded via CDN)
- Font Awesome 6.4 (loaded via CDN)
- Google Fonts - Nunito (loaded via CDN)

## Conventions
- Duolingo-inspired visual style: 3D buttons, rounded cards, bold colors (#58cc02 green, #ff4b4b red)
- Font: Nunito (bold/extra-bold weights)
- Mobile-first responsive design
- Toast notifications for user feedback
- No build tools -- pure static HTML/JS/CSS

---

_Update this file whenever the project's architecture or goals change significantly._
