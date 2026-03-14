# Task List

## Current Sprint

### Charts / Analytics Tab
- [x] Plan the charts feature
- [ ] Add Chart.js CDN and tab navigation (Tracker | Charts)
- [ ] Build daily stacked bar chart (green polite / red rude per day) with date range filtering
- [ ] Add averages-over-time view
- [ ] Add standout days detection and highlighting
- [ ] Live test in browser and iterate

**Approach:**
- Use Chart.js via CDN (no build step, keeps single-file architecture)
- Stacked bar chart style matching the reference image (value labels on each segment)
- Tab system: toggle between Tracker view and Charts view
- Date filters: Last 7 days, Last 30 days, This Month, Custom range
- Averages view: rolling average line overlaid or separate chart
- Standout days: auto-detect days with unusually high rude or polite counts, highlight them

---

## Backlog

- Wire up sound effects from `sfx/` to polite/rude actions
- Add data visualization charts (reference: `ChartStyleExample.png`)
- Daily/weekly summaries
- Trend tracking
- Reward system
- Multi-child support

---

## Completed

_Finished tasks move here with a brief result summary._

---

## Review Notes

_Post-implementation review observations go here._
