# Notification Dropdown Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a responsive YouTube-style notification panel anchored beneath the homepage bell.

**Architecture:** Keep the static notification content in `index.html`, presentation in `styles.css`, and interaction in the existing inline script at the bottom of `index.html`. The panel opens from the bell, closes from the bell, outside clicks, or Escape, and remains anchored under the bell on mobile.

**Tech Stack:** Existing HTML, CSS, and vanilla JavaScript; no new libraries.

**Spec:** `docs/superpowers/specs/2026-10-29-notifications-dropdown-design.md`

## Global Constraints

- Use static sample notifications; do not add a backend.
- Keep the notification panel beneath the bell on desktop and mobile; do not make it a full-screen sheet.
- Use the existing project files and styling patterns.

## Review Focus

- Opening the panel must not also open the mobile sidebar; keep notification and sidebar controls separate.
- Clicking inside the panel must not count as an outside click and close it.
- The panel must fit within a narrow viewport and scroll vertically when its contents exceed the available height.
- The bell must expose its expanded state and identify the panel it controls.
- Missing thumbnail or avatar images must not break the layout.

---

### Task 1: Add notification button and panel content

**Files:**
- Modify: `index.html` header markup and the existing notification area.

**Interfaces:**
- Produces: a bell button with an accessible name, `aria-expanded`, and `aria-controls`; a panel with a matching `id` and initially hidden state.

- [ ] Change the bell image into a button without changing its visible icon, then place the button and panel inside a dedicated `.notification-menu` wrapper.
- [ ] Add the panel inside `.notification-menu`, with a “Notifications” heading and settings icon.
- [ ] Add “Important” and “More notifications” groups using static sample rows with avatar, message, time, optional thumbnail, and more-options icon.
- [ ] Review the HTML structure to ensure the panel is a sibling of the bell button and both are inside `.header-right`.

### Task 2: Style the anchored panel

**Files:**
- Modify: `styles.css` notification panel rules and mobile media query.

**Interfaces:**
- Consumes: the notification button and panel markup from Task 1.
- Produces: a white panel aligned beneath the bell, with grouped rows, separators, scrollable content, and a viewport-safe width and height.

- [ ] Position `.notification-menu` relative to the bell; place the panel beneath it and align the panel’s right edge with the bell button.
- [ ] Style the heading, groups, notification rows, text, thumbnails, and row separators to match the reference.
- [ ] Set a maximum panel height with vertical scrolling, and constrain its width on small screens so it stays within the viewport.
- [ ] Review the panel at desktop and mobile widths for clipping and overlap.

### Task 3: Add open and close behavior

**Files:**
- Modify: the existing inline script at the bottom of `index.html`.

**Interfaces:**
- Consumes: the notification button and panel identifiers from Task 1.
- Produces: bell click toggles the panel and `aria-expanded`; outside click and Escape close the panel and reset `aria-expanded`.

- [ ] Add a click handler for the notification button that opens or closes only the notification panel.
- [ ] Close the panel when a click occurs outside both the button and the panel; clicks inside the panel should leave it open.
- [ ] Close the panel on Escape and keep `aria-expanded` in sync for every close path.
- [ ] Review that the existing sidebar open and close handlers still work independently.
