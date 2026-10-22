# Security and privacy check

Checked on 10 Oct 2026, and re-checked on 22 Oct 2026, against `index.html` in this repository.

## Summary

- **Fully self-contained.** Every image, icon, chart, font, video and sound is inside `index.html`. The page makes no requests to any other server.
- **No malware, trackers or hidden code.** There is no `eval`, `new Function`, `atob`, `document.write`, `fetch`, `XMLHttpRequest`, WebSocket, beacon, service worker, cookie, local storage, iframe, pop-up window, or form that posts anywhere.
- **No device permissions.** The page never asks for the camera, microphone, location, notifications or clipboard. The "voice" and "dictation" in the demo are simulated.
- **Locked down by a Content-Security-Policy.** The browser refuses any remote script, image, font, media, frame or connection, even if someone tried to add one.

## What changed

| | Before | After |
|---|---|---|
| Fonts (Roboto, Lato, Sora, Source Serif 4, Roboto Mono) | Loaded from Google Fonts: 50 requests to `fonts.googleapis.com` and `fonts.gstatic.com` in a test session | Embedded in the page (latin subset, about 290 KB) |
| Link to modelcontextprotocol.io | Clickable link to an outside site | Plain text |
| Read-aloud voice | Browser default voice, which can be a cloud voice in some browsers | Uses an on-device voice when one is available |
| Content-Security-Policy | None | `default-src 'none'`; scripts allowed only by SHA-256 hash; images, media and fonts only from `data:` and `blob:`; no connections, frames, workers, objects or form posts |
| Referrer | Browser default | `no-referrer` |
| Favicon | Browsers may request `/favicon.ico` | Empty inline icon, so there is nothing to fetch |

Images, icons, charts, video briefs and video posters were already inline (`data:` URIs, inline SVG, or drawn on the page), so they needed no change.

## How it was verified

The page was opened in headless Chromium at laptop size and at iPhone 13 size, with every network request logged. The test went through all five chat apps, signed in on WhatsApp, played a video brief, opened the secure view and triggered an alert.

- **Before:** 50 requests to Google Fonts per session.
- **After:** zero requests to any other origin. The only request is the page itself.
- **CSP violations during normal use:** none. All five fonts still load.
- **Blocking test:** adding a remote image, script and `fetch` call from the browser console was refused by the CSP (`img-src`, `script-src-elem`, `connect-src`).

## Things the page does use

- **Sound:** a short chime generated in the page with the Web Audio API. It plays only after the viewer has tapped or typed once, as browsers require.
- **Vibration:** a short buzz on phones when an alert arrives, where the browser supports it.
- **Speech:** the browser's built-in text-to-speech reads some answers aloud when you press play.

## Data

All data is fictional sample data for a made-up company. Nothing is collected, stored or sent anywhere.
