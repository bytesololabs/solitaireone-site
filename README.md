# solitaireone-site

Static site hosting the public surface for the Solitaire One Android app.

Lives at **https://solitaireone.bytesololabs.com**.

## Purpose

1. **Share-receive landing page** — `/g?g=<token>` renders a "your friend
   shared a deal" page with an **Open in app** button (custom scheme
   `solitaireone://g?g=<token>`) and a Google Play CTA fallback.
2. **Android App Links verification** — `/.well-known/assetlinks.json`
   tells Android that this domain is authorized to deep-link directly
   into the Solitaire One app (skipping the browser chooser).
3. **Generic landing** — `/` shows a small intro + Play Store link for
   anyone who lands on the bare host.

## Hosting

Deployed via GitHub Pages from the `main` branch root (no build step,
pure static HTML/CSS/JS). DNS `CNAME` `solitaireone` points at
`bytesololabs.github.io` in Hostinger.

## Files

| Path | Purpose |
| --- | --- |
| `CNAME` | GitHub Pages custom-domain binding |
| `index.html` | Bare-host landing page |
| `g/index.html` | Share-receive landing page (token in `?g=`) |
| `.well-known/assetlinks.json` | Android App Links proof of ownership |
