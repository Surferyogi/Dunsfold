# Dunsfold Renovation & Move — PWA Setup

A shared renovation and move tracker for CK & Sophia. Works offline once installed.

Tap any task to open its detail page: edit the title, keep notes, and log entries
(e.g. one row per contractor quote — star the one you pick).

## What's in this folder

| File | Purpose |
|---|---|
| index.html | The entire app (all logic and styling in one file) |
| sw.js | Service worker — makes the app work offline |
| manifest.json | Makes the app installable to your phone's home screen |
| icon-192.png / icon-512.png | App icons |

## Hosting (pick ONE — takes under 5 minutes)

A PWA must be served over HTTPS from a real web address. Any free static host works:

**Option A — Netlify Drop (easiest, no account needed to start)**
1. Go to https://app.netlify.com/drop
2. Drag this whole folder onto the page
3. You get a live URL immediately (e.g. https://something.netlify.app)

**Option B — GitHub Pages**
1. Create a new GitHub repository, upload these 5 files
2. Settings → Pages → Deploy from branch → main → root
3. Your app is at https://<username>.github.io/<repo>/

**Option C — Cloudflare Pages / Vercel** — drag-and-drop the folder in their dashboard.

## Installing on your phones

Once hosted, open the URL on each phone:

- **iPhone (Safari):** Share button → "Add to Home Screen"
- **Android (Chrome):** You'll see an "Install" bar at the bottom of the app, or use menu → "Install app"

After installing, the app opens full-screen like a native app and works offline.

## Keeping CK & Sophia in sync

Data is stored on each device separately (there is no server). To sync:
1. Person with the latest changes taps **Export** — this downloads a small .json file
2. Send it via WhatsApp/AirDrop/email
3. The other person taps **Import** and picks that file

Tip: do a quick export/import at the end of any day where both of you made changes.

## Changing the task list defaults

The pre-loaded tasks live inside index.html in the `SEED` block near the top of the
script. Edit the text there before hosting if you want different defaults. Once the app
has been used on a device, it loads from that device's saved data, not the seed.
