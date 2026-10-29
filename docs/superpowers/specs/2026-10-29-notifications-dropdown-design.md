# Notification dropdown design

## Intent

Add a YouTube-style notifications panel to the homepage. Tapping the bell opens a panel beneath it, matching the user's reference image.

## Goals

- Show a "Notifications" heading and settings icon.
- Show grouped notification rows with an avatar, message, time, optional thumbnail, and more-options icon.
- Keep the panel anchored below the bell on desktop and mobile; allow its contents to scroll when they exceed the available height.
- Close the panel when the bell is tapped again or the user taps outside it.

## Non-goals

- Connecting to real notifications or a backend; use static sample notifications.
- Building a separate notifications page or full-screen mobile sheet.

## Approaches

- Anchored dropdown panel: matches the reference and leaves the page visible behind it. **Chosen**, based on the user's reference and preference to keep it beneath the bell on mobile.
- Full-screen mobile sheet: gives more room on small screens, but does not match the requested reference.

## Implementation notes

Build with the existing HTML, CSS, and JavaScript. The bell is currently an image, so it will need to be made an accessible button, with a panel element and toggle behavior. Use static placeholder content and responsive width/height limits so the panel fits the viewport.
