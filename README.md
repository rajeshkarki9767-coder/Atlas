# Atlas · v3.8

A complete personal growth tracker — goals, habits, wins, journal — as a single self-contained HTML file with full PWA support.

## What's in this bundle

| File | Purpose |
|---|---|
| **`index.html`** | The complete app · 164 KB · open in any browser |
| `atlas-icon.svg` | Vector source for the app icon · 1 KB |
| `atlas-icon-192.png` | 192×192 PNG · for PWA manifest |
| `atlas-icon-512.png` | 512×512 PNG · for iOS / large displays |
| `atlas-icon-1024.png` | 1024×1024 PNG · App Store / max resolution |

## Quick start

1. Open `index.html` in any modern browser (Safari, Chrome, Firefox, Edge)
   - Or double-click the file — your default browser will open it
2. Complete the 3-step onboarding (name → starter habits → tip)
3. Start tracking

## Installing as an app

Atlas works as a Progressive Web App — install it to get the full-screen, no-browser-chrome experience just like a native app.

### iPhone / iPad (Safari)
1. Open `index.html` in **Safari** (must be Safari, not Chrome)
2. Tap the **Share button** at the bottom of the screen
3. Scroll down and tap **"Add to Home Screen"**
4. Tap **"Add"** in the top-right corner
5. The Atlas icon appears on your home screen — tap it to launch full-screen

### Android (Chrome)
1. Open `index.html` in Chrome
2. A banner appears at the top — tap **"Install"**
   - Or: tap the three-dot menu → **"Install app"** / **"Add to Home Screen"**
3. Confirm the install dialog

### Desktop (Chrome / Edge)
1. Open `index.html` in Chrome or Edge
2. Look for the **install icon** ⊕ in the address bar
3. Click it and confirm
4. Atlas launches as a standalone desktop app

The app also includes an **install guide** built into Settings → App that detects your platform and shows specific instructions.

## Hosting on the web (optional)

Since the main file is `index.html`, you can host the bundle anywhere — GitHub Pages, Netlify, Vercel, your own server. Drop the entire folder in your hosting service and visiting the URL automatically loads `index.html` (no path needed).

## Features

**Tracking**
- Goals with units (days, books, $, km, etc.), deadlines, sub-tasks, pinning, search/sort/filter
- Habits with 5 frequency presets + custom day picker
- Wins (achievements) with auto-medals
- Journal with mood picker
- GitHub-style heatmap per habit
- 11 auto-awarded badges

**Polish**
- Onboarding flow for first-time users
- Long-press habit days to skip with reason (sick, traveling, rest day, other)
- Sound + haptic + confetti feedback (all toggleable)
- Animated stat counters
- Dark / Light theme + 5 accent palettes + custom color picker
- 3-dropdown DOB picker (Day / Month / Year) instead of clunky native picker

**Data**
- Persistent storage across sessions
- JSON export / import for backups
- Reset all data with confirmation
- 32+ Discover suggestions including 14-item sobriety pack

## Browser requirements

- Modern browser with ES2020+ support (Safari 14+, Chrome 90+, Firefox 90+, Edge 90+)
- ~200 KB free local storage
- For full PWA install: HTTPS or localhost (file:// works for Safari "Add to Home Screen" on iOS)

## Privacy

100% local. Nothing leaves your device. No accounts, no analytics, no tracking, no cloud sync. Your data lives in your browser's storage and only there. Use the export feature to back up.

## Version 3.8 changelog

- App icon added to the top-left of the main page (tap to return to dashboard)
- Fixed broken inline SVG icons in welcome screen and footer (rect width attributes were inheriting wrong values)
- Unique gradient IDs across all 3 inline icons (no more SVG ID collisions)

## Version 3.7 changelog

- Code cleanup: removed dead/redundant code paths in DOB picker
- Strict-mode validated (zero implicit globals, zero undeclared variables)
- All 14 critical user flows traced end-to-end and verified

## Version 3.6 changelog

- Cross-platform PWA install (iOS guided modal + Chrome prompt + desktop instructions)
- App icon embedded inline + 4 standalone icon files
- Custom 3-dropdown DOB picker
- Cleaner Settings layout with action rows and stat tiles
- Clean professional fonts (Manrope + Inter + JetBrains Mono with Calibri fallback)
- Main file renamed to `index.html` for standard web hosting
- All previous v3 features intact
