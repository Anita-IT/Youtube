# Create Dropdown Implementation Plan

> **For agentic workers:** This plan is for the user to follow step by step; do not edit the project files on their behalf.

**Goal:** Add a Create dropdown to the homepage that matches the reference and shows three inactive options.

**Architecture:** Wrap the existing Create button in a positioned container and place a hidden panel beside it in the header. On mobile, center the panel and show a dim backdrop. Toggle both with JavaScript, following the existing hidden-panel pattern.

**Tech Stack:** HTML, CSS, and the existing vanilla JavaScript and Font Awesome setup.

**Spec:** [Create dropdown design](../specs/2026-10-30-create-dropdown-design.md)

## Global Constraints

- Modify only `index.html` and `styles.css` for the feature.
- Keep the three menu rows inactive.
- Preserve the existing header controls and layout.

## Review Focus

- The menu starts hidden and the Create button opens and closes it.
- Clicking the menu rows does not navigate or trigger an action.
- The panel appears beneath Create and layers above the category bar and video content.
- On mobile, the panel is centered, the page is dimmed, and clicking the backdrop closes it.
- The panel remains inside the viewport at narrow widths.
- Existing notification and profile menus continue to use their own controls.

---

### Task 1: Add the menu structure

**Files:**
- Modify: `index.html` (the `.header-right` Create button and its surrounding markup)

- [ ] Wrap the existing Create button in a uniquely named wrapper and give the button `type="button"`, an accessible label, `aria-expanded="false"`, and an `aria-controls` value matching the new panel ID.
- [ ] Add a panel with that ID and the `hidden` attribute, containing the three visual rows: Upload video, Go live, and Create post. Use the project's Font Awesome icons; do not add click handlers to the rows.
- [ ] Add a hidden backdrop button inside the wrapper, before the panel.
- [ ] Check that the wrapper and panel close before the notification-menu markup begins.

### Task 2: Style and position the panel

**Files:**
- Modify: `styles.css` (after the existing header control styles)

- [ ] Make the wrapper a positioning context and position the panel below the Create button, with a white background, rounded corners, shadow, and a stacking level above the category bar.
- [ ] Style each row as a horizontal icon-and-label line with spacing and a hover background, without changing the existing Create button dimensions.
- [ ] Add a hidden-state rule so the panel's display styling cannot override its `hidden` attribute.
- [ ] Add a narrow-screen width constraint so the panel stays within the viewport.
- [ ] At mobile widths, position the panel in the viewport center and show the fixed dim backdrop behind it.

### Task 3: Toggle the panel

**Files:**
- Modify: `index.html` (the script at the bottom)

- [ ] Select the Create button and panel by their new selectors.
- [ ] Add a button click handler that toggles the panel's `hidden` property and updates `aria-expanded` to match.
- [ ] Toggle the backdrop with the panel; clicking the backdrop hides both and resets `aria-expanded` to `false`.
- [ ] Leave the three menu rows without action handlers.
- [ ] In the browser, check that Create opens and closes the panel, the rows remain inactive, and the panel fits on a narrow screen.
