# Create Dropdown Design

## Intent

Add the Create dropdown shown in the reference to the homepage header, with Upload video, Go live, and Create post rows.

## Behavior

The Create button toggles a hidden panel. The three rows are visual options only and have no action. On desktop, the panel sits beneath the Create button. On mobile, it is centered in the viewport over a dim backdrop. Clicking the backdrop closes the panel.

## Approach

Use the existing button plus `hidden` panel pattern already used by the homepage profile and notification menus. Keep the change in `index.html` and `styles.css`; use the existing Font Awesome icons. Do not change the watch page or other header controls.

## Constraints

Keep the existing header layout. Do not attach click actions to the three menu rows.
