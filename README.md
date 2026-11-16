# YouTube UI Clone

A responsive, front-end recreation of the YouTube browsing experience. The project is built with plain HTML, CSS, and a small amount of inline JavaScript—no build tools or package installation required.

## Pages

- `index.html` — home feed with category filters, video cards, Shorts, sidebar navigation, Create menu, notifications panel, and profile menu.
- `watch.html` — video watch layout with a poster-style player, metadata, actions, description, recommendations, and a responsive sidebar.

## Features

- Responsive desktop and mobile layouts
- Collapsible mobile sidebar with backdrop controls
- Create, notification, and profile dropdown menus on the home page
- Scrollable navigation and profile-menu areas
- Home-feed cards that link to the watch page
- Local thumbnail, icon, and avatar assets in `image/`
- Keyboard-visible focus styles for video links and watch-page controls

## Getting started

Clone or download the project, then open `index.html` in a modern web browser:

```bash
git clone <repository-url>
cd Youtube
open index.html
```

Alternatively, use your editor's local development server (for example, VS Code Live Server) and open the served `index.html` page.

No dependencies need to be installed.

## Project structure

```text
.
├── index.html       # Home page and its menu interactions
├── watch.html       # Video watch page and sidebar interaction
├── styles.css       # Shared responsive styles
├── image/           # Local UI icons, thumbnails, and avatars
└── docs/            # Design notes and implementation plans
```

## External resources

The interface loads the following resources over the network:

- [Roboto](https://fonts.google.com/specimen/Roboto) from Google Fonts
- [Font Awesome](https://fontawesome.com/) icons via a kit script

An internet connection is needed for those fonts and icons to render as intended. All image assets are stored locally.

## Notes

This is a UI prototype, not a working video platform. Search, upload, playback, account actions, and most buttons are presentational only. The watch player is a visual preview rather than a connected video player.

## License

No license has been specified for this project. Add one before distributing or reusing it outside this repository.
