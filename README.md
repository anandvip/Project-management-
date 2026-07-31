# Project-management-
Project management single page tool 

# Flowboard — Project Tracker

**Date created:** 2026-07-30
**Tool:** Claude Sonnet 5 (claude.ai)
**Prompt used:** "A working tool that provides the functionality of Kaneo (self-hosted kanban
project management). Single-file HTML/CSS/JS. Solo-use focused (no team/notifications
overhead): Projects → Tasks → Kanban status columns → Labels → optional due dates,
plus a Someday/Ideas bucket so half-formed ideas don't clutter active boards.
localStorage persistence, mobile-first, no external dependencies."

## Purpose

A single-file, offline-capable kanban board for tracking personal projects (e.g. FD
calculators, admin hierarchy visualizations, negotiation tools) without the overhead of
a hosted, team-oriented PM tool like Kaneo, Trello, or Asana.

## Core features

- **Multiple projects** — switch between them via the top scrollable rail. Each chip
  shows a small ring gauge indicating % of active tasks marked Done.
- **Kanban columns** — To Do / In Progress / In Review / Done. Drag cards between
  columns, or tap a card to edit its status directly.
- **Someday / Ideas drawer** — a collapsed bucket for tasks that aren't ready to be
  "active" yet, so the main board stays uncluttered. One tap promotes an idea to To Do.
- **Labels** — freeform tags (e.g. research, build, fix, client-facing) managed from a
  dedicated panel; filterable visually via colored pills on each card.
- **Due dates** — optional; overdue tasks are flagged in red on their card.
- **Persistence** — all data (projects, tasks, labels) is stored in `localStorage` under
  the key `flowboard_data_v1`. No server, no account, no external requests.

## Notes for future maintenance

- Data model: `{ activeProjectId, projects: [{id, name, createdAt}], labels: [string],
  tasks: [{id, projectId, title, notes, status, due, labels, createdAt}] }`.
- Status values: `someday`, `todo`, `doing`, `review`, `done`.
- No build step — open `flowboard.html` directly in any modern browser.

