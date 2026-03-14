# Lessons Learned

Rules and patterns accumulated from corrections and mistakes. Review at session start.

---

## Rules

### [Persistence] -- Always include localStorage for local-only mode
**Trigger:** User tested on mobile, data disappeared on reload because only in-memory storage was used
**Rule:** Any data that users create must persist to localStorage by default. Firebase is optional/additive.
**Date:** 2026-03-13

### [Deployment] -- Always update gh-pages after pushing to master
**Trigger:** GitHub Pages serves from gh-pages branch, not master
**Rule:** After pushing changes to master, merge into gh-pages and push to deploy the live site.
**Date:** 2026-03-13

---

## Patterns

- Single-file architecture works well for rapid iteration -- keep it unless complexity demands splitting
- Always test on the live GitHub Pages URL on mobile after deploying
- Use `npx serve` for local dev testing
