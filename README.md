# Atlas · v4.3

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

## Version 4.3 changelog

- **Real "A" letterform.** Redesigned the icon from a chevron-with-stick into a proper geometric capital A with two diagonal legs and a real crossbar. Updated the SVG source, all 3 PNG sizes (192/512/1024), and all 3 inline SVGs in the app (topbar / welcome / footer).
- **Manifest now references PNG files.** Previously used base64 SVG data URLs which some Android versions reject for PWA install. Now the manifest points to `atlas-icon-192.png`, `atlas-icon-512.png` (both `any` and `maskable` purposes), and `atlas-icon.svg` as fallback. **This is the key fix for the Chrome badge issue when installed from a hosted URL.**
- **Apple touch icons added.** New `<link rel="apple-touch-icon">` and `<link rel="icon">` entries so iOS Safari and Android Chrome use the real icon files for home-screen install instead of generating one from a screenshot.
- **Smaller manifest.** Went from ~6500 chars (3 base64 SVGs embedded) to 1096 chars referencing the bundled PNGs.

## Version 4.2 changelog

- **Undo for accidental taps:** When you tap "Done" on a habit, the toast now has an "Undo" button (visible for 2 seconds). Taps work both ways — mark and unmark.
- **Past days are now read-only on the dashboard week strip and heatmap.** Only today is tappable. Past dates show a hint: "Long-press the row to backdate or skip" — keeping the intentional path through the long-press action menu.
- **Cleaned up duplicate `.toast.show` CSS rule.**

## Version 4.1 changelog

Major feature update — 12 new capabilities across the app:

**Editing & corrections**
- Edit wins (titles + descriptions) without losing them
- Edit journal entries — text and mood — anytime
- Edit goal progress directly with a number input (no more endless +/− tapping)

**Backdate habits**
- Long-press any habit row on the dashboard to open an action menu
- Mark for today / yesterday / pick any past date / skip with reason / view stats

**Streak freezes**
- Earn 1 freeze every 14-day streak (max 3 banked)
- Auto-applied to protect a single missed day if your streak is ≥ 7
- Frozen days display with a 🛡 badge in heatmap

**Goal milestones**
- When sub-tasks count meets goal target, they become trackable milestones
- Header shows "Milestones · 5/12" with auto-progress sync
- Better placeholder text guides milestone naming

**Calendar & review screens**
- New **Calendar** view with month-by-month activity dots (habits, wins, journal, freezes)
- New **Weekly Review** with overall %, activity-by-day chart, per-habit breakdown
- Both accessible from the Home tab

**Year heatmap**
- GitHub-style 53-week contribution graph per habit
- Toggle from any habit's detail page

**Drag-to-reorder**
- "Reorder" button on Goals and Habits tabs enters reorder mode
- HTML5 drag on desktop + custom touch drag on iOS/Android
- Visual drop indicators, haptic feedback

**Unified search**
- Magnifier button in topbar opens full-screen search
- Searches across goals, habits, wins, and journal in one query
- Highlights matching terms inline

**Notifications & reminders**
- Browser notifications when Atlas is running (Settings → Notifications)
- Daily reminder at your chosen time (default 9pm)
- Per-habit reminder times in habit edit modal
- Notification action handlers (when used with service worker)

**Offline support**
- Inline service worker caches the app for offline access
- Network-first for HTML, cache-first for assets
- Only registers when served from HTTP/HTTPS (not file://)

**Polish**
- Better empty states with hints throughout
- Frozen heatmap cells styled distinctly

## Version 4.0 changelog

- **Multi-tier storage system:** Now uses IndexedDB → localStorage → window.storage cascade. Previously only localStorage which can be unreliable on Android `file://` URLs. IndexedDB is far more durable.
- **Auto-save on app close:** Saves state when the tab is hidden (`visibilitychange`), the page is unloaded (`pagehide`), or the browser is closing (`beforeunload`). Insurance against data loss.
- **Storage diagnostics:** New "Storage" entry in Settings → Data shows you exactly which backends are working, how much data is stored, when the last save happened, and runs live read/write tests. If something is broken, you'll see it instantly.
- **Goal deadline picker (v3.9 follow-up):** Custom 3-dropdown picker working alongside DOB picker.

## If data still won't persist

Open Settings → Data → **Storage** in the app. The diagnostics modal will tell you exactly what's happening. Common causes:

1. **`file://` URL on Android Chrome** — Android may treat localStorage as session-only when the file is opened directly. **Fix:** host the file (Netlify Drop, GitHub Pages — see below).
2. **Private/incognito mode** — storage clears when you close the tab. Open the file in a normal tab.
3. **"Clear browsing data"** — wipes the app's storage too. Use Export regularly.
4. **Browser storage quota exceeded** — unlikely (~200 KB needed) but possible with huge journals.

## Version 3.9 changelog

- **Storage fix:** Now uses `localStorage` as primary (works on installed PWA and any browser). Previous versions used a Claude artifact API that doesn't exist on your phone, causing data loss on install.
- **Goal deadline picker:** Replaced clunky native date input with the custom 3-dropdown picker (Day / Month / Year) — same as DOB picker, no more stuck-open native overlay.
- **Better PWA manifest:** Added `id`, `scope`, `orientation`, `description`, `categories`, and proper `purpose: maskable` for the install icon.
- **Chrome logo explainer:** New note in install guide — if you see the Chrome badge on your icon, it means the file was installed as a shortcut. Host it on GitHub Pages / Netlify / Vercel for a clean install.

## Why hosting matters for the icon

When you double-click an HTML file and use Chrome's "Add to Home Screen", Android creates a **bookmark shortcut** (with the Chrome logo overlay), not a true PWA. To get the gold-A icon without any badge, the file needs to be served from a real URL. Free options:

- **GitHub Pages:** create a repo, upload `index.html` + the icon files, enable Pages → instant URL
- **Netlify Drop:** drag the folder to netlify.com/drop → instant URL
- **Vercel:** `vercel deploy` from the folder

Once installed from a real URL, the icon will be clean.

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
