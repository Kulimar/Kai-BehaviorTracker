# CLAUDE.md

## Project Identity

**Owner:** Seda (kdak)
**Project:** Kai's Behavior Tracker
**Stack:** HTML, CSS (Tailwind CDN), JavaScript (vanilla), Firebase (Auth + Firestore), Font Awesome
**Repo:** BehaviorTracker

A Duolingo-inspired behavior tracking web app for a child named Kai. Tracks polite vs rude choices with counters, notes, history timeline, sound effects, and Firebase-backed persistence. Designed for mobile-first use by parents/caregivers.

---

## Workflow Orchestration

### 1. Plan Before Execute

Enter plan mode for ANY task involving 3+ steps, architectural decisions, or complex analysis.

Plans must include:
- Task breakdown with checkable items
- Expected outputs
- Verification steps

**If something goes sideways -- STOP -- Re-plan. Do not push through a broken plan.**

Write plans to `tasks/todo.md`. Get confirmation before implementing.

### 2. Subagent Strategy

Use subagents to keep the main context window clean:
- Offload research, exploration, and parallel analysis
- One focused responsibility per subagent
- For complex problems, throw more compute at it -- spawn multiple subagents

### 3. Self-Improvement Loop

After ANY correction from the user:
1. Record the pattern in `tasks/lessons.md`
2. Write a rule preventing the same mistake
3. Review `tasks/lessons.md` at the start of every session

This is non-negotiable. The goal is zero repeat mistakes.

### 4. Verification Before Done

A task is **never complete** until it is verified.

Verification includes:
- Build/compile passes
- Tests pass (or manual demonstration of correctness)
- Diff review against main when relevant
- Log inspection for errors or warnings

Ask: *"Would a staff engineer approve this?"*

### 5. Demand Elegance (Balanced)

For non-trivial changes: pause and ask "is there a more elegant way?"

- If a fix feels hacky -- step back -- implement the clean solution
- Skip this for simple, obvious fixes -- don't over-engineer
- Prefer clear, maintainable approaches over clever ones

### 6. Autonomous Bug Fixing

When given a bug report:
- Inspect logs, errors, failing tests
- Identify root cause
- Fix it directly

Do not ask for hand-holding. Zero context-switching required from the user.

---

## Task Management Lifecycle

1. **Plan First** -- Write plan to `tasks/todo.md` with checkable items
2. **Verify Plan** -- Check in with the user before starting implementation
3. **Track Progress** -- Mark items complete as you go
4. **Explain Changes** -- High-level summary at each step
5. **Document Results** -- Add review section to `tasks/todo.md`
6. **Capture Lessons** -- Update `tasks/lessons.md` after corrections
7. **Save Prompts** -- Log significant prompts to `tasks/prompts.md` so work is reproducible

---

## Core Principles

**Simplicity First** -- Make every change as simple as possible. Minimal code impact. Easy to understand and maintain.

**Root Cause Focus** -- No temporary fixes. Find and solve the underlying issue. Senior developer standards.

**Minimal Impact** -- Changes touch only what's necessary. Avoid introducing regressions.

---

## Session Protocol

### Starting a Session

1. Read this file
2. Read `tasks/lessons.md` -- check for relevant patterns
3. Read `tasks/todo.md` -- surface current state
4. Load project context from `projects/project-context.md` (if applicable)
5. Confirm what we're working on before doing anything

### Ending a Session

1. Update `tasks/todo.md` with current state
2. Write session summary (what was done, what's next, any blockers)
3. Capture any new lessons in `tasks/lessons.md`
4. Commit changes with a descriptive message

---

## Architecture Notes

- **Single-file app:** All HTML/CSS/JS lives in `index.html`
- **Firebase integration:** Uses anonymous auth + Firestore for cloud persistence
- **Local fallback:** Works without Firebase config (in-memory mode)
- **Sound effects:** MP3 files in `sfx/` directory (Positive1-4, Rude1-4, jigs)
- **Styling:** Tailwind CSS via CDN + custom 3D button styles (Duolingo-inspired)
- **Mobile-first:** Responsive layout, touch-friendly buttons, keyboard dismissal on action

---

## Asset & Configuration Management

When the project has assets (images, sprites, sounds, configs, data files):
- Maintain an `assets-index.json` or equivalent manifest as the canonical source of truth
- Update the manifest whenever assets are added, removed, or reorganized
- Reference the manifest rather than traversing directories each time

---

## Key File Locations

| File | Purpose |
|---|---|
| `CLAUDE.md` | This file. System instructions for Claude Code. |
| `index.html` | The entire application (single-file web app) |
| `sfx/` | Sound effect MP3 files for polite/rude feedback |
| `ChartStyleExample.png` | Reference image for chart styling |
| `tasks/todo.md` | Active task list with checkable items |
| `tasks/lessons.md` | Accumulated patterns and mistakes to avoid |
| `tasks/prompts.md` | Log of significant prompts for reproducibility |
| `projects/project-context.md` | Project-specific context, goals, constraints |
| `_scratchpad.md` | Loose ideas not yet assigned to a project or task |
| `docs/specs/` | Architecture specs and design docs |

---

## Agent System (Optional)

Specialist agents live in `.agents/agents/` and can be invoked for focused work:

| Agent | Responsibility |
|---|---|
| `coordinator` | Session start/end, delegation, progress tracking |
| `research-agent` | Investigation, information gathering, analysis |
| `design-agent` | Architecture, system design, conceptual models |
| `implementation-agent` | Building, coding, executing plans |
| `review-agent` | Validation, critique, verification, testing |
| `documentation-agent` | Writing docs, summaries, structured reports |

Invoke agents when the task benefits from focused context isolation. For simple tasks, work directly without agent overhead.

---

## Skills (Optional)

Custom skills live in `.agents/skills/`. Each skill folder contains a `SKILL.md` with:
- Purpose and trigger conditions
- Requirements and dependencies
- Expected output format
- Step-by-step instructions

Skills are loaded on-demand when relevant to the current task.

---

## Commit Conventions

- Use conventional commits: `feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`
- Include scope when useful: `feat(auth): add JWT token refresh`
- Keep messages descriptive but concise
- Claude can generate commit messages, but the user may prefer to write their own when moving fast

---

## What NOT to Do

- Don't implement without a plan for non-trivial work
- Don't mark tasks done without verification
- Don't make the same mistake twice -- that's what `lessons.md` prevents
- Don't ask unnecessary clarifying questions when the intent is clear
- Don't over-engineer simple problems
- Don't hard-code values that should be configurable
