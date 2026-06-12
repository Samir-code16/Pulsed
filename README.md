# Pulsed — Productivity PWA

A mobile-first Progressive Web App for students, founders, and doers.  
Track habits, manage goals, scan documents with AI, and share data via QR code.

---

## Features

- **Activity Tracker** — daily habits with streaks, animated check-ins, and a live progress ring
- **Goals** — assignments, deadlines, and weekly targets with progress tracking
- **AI Scanner** — snap or upload any image; Claude analyses it instantly
- **Notes** — all scan results saved and searchable
- **QR Share** — generate QR codes for your data and download them

---

## Setup — Add your API key

Before deploying, open `index.html` and replace the placeholder on this line near the top of the `<script>` block:

```js
const ANTHROPIC_API_KEY = 'YOUR_API_KEY_HERE';
```

Replace `YOUR_API_KEY_HERE` with your Anthropic API key.  
Get one at: https://console.anthropic.com

> **Important:** For a production app, never expose your API key in client-side code.  
> Instead, route API calls through a small backend (e.g. a Vercel Edge Function or Cloudflare Worker) that holds the key securely. For personal/prototype use, the direct key approach is fine.

---

## Deploy to GitHub Pages (step-by-step)

### Step 1 — Create a GitHub account
If you don't have one, sign up free at https://github.com

### Step 2 — Create a new repository
1. Click the **+** icon in the top-right corner → **New repository**
2. Name it `pulsed` (or anything you like)
3. Set visibility to **Public**
4. Click **Create repository**

### Step 3 — Upload the files
1. In your new repo, click **Add file** → **Upload files**
2. Upload all four files and the `icons/` folder:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icons/icon-192.png`
   - `icons/icon-512.png`
3. Scroll down and click **Commit changes**

### Step 4 — Enable GitHub Pages
1. Go to your repo's **Settings** tab
2. In the left sidebar, click **Pages**
3. Under **Source**, select **Deploy from a branch**
4. Set the branch to **main** and folder to **/ (root)**
5. Click **Save**

### Step 5 — Get your live URL
After about 60 seconds, GitHub will show you a green banner with your live URL:
```
https://YOUR_USERNAME.github.io/pulsed/
```

That's your live PWA. Share this link with anyone.

---

## Install on iPhone (Add to Home Screen)

1. Open your GitHub Pages URL in **Safari** on iPhone
2. Tap the **Share** button (the box with an arrow pointing up)
3. Scroll down and tap **Add to Home Screen**
4. Tap **Add**

The app now appears on your home screen like a native app — full screen, no browser UI.

---

## App Icons

The `icons/` folder needs two PNG files:
- `icon-192.png` — 192×192 pixels
- `icon-512.png` — 512×512 pixels

Use any image editor (or a free tool like https://favicon.io) to create a simple icon with the Pulsed logo on a deep purple `#534AB7` background.

---

## File structure

```
pulsed/
├── index.html       ← Full app (HTML + CSS + JS)
├── manifest.json    ← PWA install metadata
├── sw.js            ← Service worker (offline support)
├── icons/
│   ├── icon-192.png ← App icon (192×192)
│   └── icon-512.png ← App icon (512×512)
└── README.md        ← This file
```

---

## Tech stack

- Vanilla HTML, CSS, JavaScript — no frameworks, no build step
- [Tabler Icons](https://tabler-icons.io) — icon font
- [QRCode.js](https://github.com/davidshimjs/qrcodejs) — QR code generation
- [Anthropic Claude API](https://docs.anthropic.com) — AI image analysis
- GitHub Pages — free static hosting

---

## Camera permissions on iOS

When a user taps **Camera** in the scanner for the first time, Safari will show a native permission prompt.  
If they deny it, they can re-enable it in:  
**Settings → Safari → Camera → Allow**
