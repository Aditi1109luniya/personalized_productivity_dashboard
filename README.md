# Productivity Dashboard

A simple, single-page productivity dashboard built with vanilla HTML, CSS, and JavaScript (plus Bootstrap 5 and Font Awesome). No build tools or backend required — just open it in a browser.

## Features

- **Personalized greeting & clock** — live time-of-day greeting and ticking clock.
- **User profile** — enter your name once; it's remembered along with a color-coded avatar (initials on a color derived from your name).
- **Dark / light mode** — toggle switch, preference saved across visits.
- **Location widget** — get your location via browser GPS, or by IP lookup (via the free `geolocation-db.com` API).
- **To-do list** — add, complete, edit (double-click a task), delete, and filter tasks (All / Pending / Completed). Tasks persist in `localStorage`.
- **Daily motivational quote** — a random quote on each load.
- **Quick notes** — a scratchpad textarea that autosaves as you type.

All data (name, theme, tasks, notes) is stored in the browser's `localStorage`, so it's private to your device/browser and doesn't require any server or database.

## Project structure

```
.
├── index.html    # Page markup
├── style.css     # Styling (light + dark theme)
└── script.js     # All interactivity/logic
```

## Getting started

1. Clone or download this repo.
2. Open `index.html` directly in your browser — or serve it locally, e.g.:
   ```bash
   npx serve .
   # or
   python3 -m http.server 8000
   ```
3. Enter your name when prompted, and start adding tasks!

## Notes / known limitations

- The "Get Location by IP" button relies on the free `geolocation-db.com` API, which is unauthenticated and occasionally rate-limited or unavailable. GPS-based location ("Get My Location") is more reliable if your browser grants permission.
- Data is stored per-browser via `localStorage`; it won't sync across devices or browsers.
- This is a front-end-only demo project — there is no backend, authentication, or data persistence beyond the browser.

## Fixes applied in this version

- Task text is now HTML-escaped before rendering, so entering things like `<` or `"` in a task no longer breaks the layout.
- Avatar color is now derived from your name (stable) instead of randomizing on every page load.
- Added an empty-state message when the task list (or a filtered view) has no items.
- Delete animation (`.deleting` fade/slide) now has matching CSS so tasks visibly animate out.

## License

Free to use and modify for personal or educational purposes.
