# Playout

Producer-driven OBS overlay for podcasts. One Browser Source, three graphics off one control page — synced live over Firebase (no server, no refresh on air).

- **Host lower thirds** — name + role, slide in bottom-left. Save hosts as one-click presets.
- **Topic / Question card** — producer types a topic or question, pushes it to screen (red pill = topic, yellow = question).
- **Ticker** — scrolling bar for messages, sponsor reads, "up next"; optional live RSS headlines.

Branded to the Jomboy Media design system: Bebas Neue + Sofia Sans Semi Condensed, red `#E40000`, navy surfaces, cyan/yellow accents.

## Use

1. Open **`Playout_Control.html`** in a browser (producer's machine).
2. Set a secret **Topic** (bottom of the page) so only you can post.
3. Copy the **OBS Browser Source URL** and add it as one Browser Source in OBS at **1920×1080**.
4. Drive the show from the control page — lower thirds, topic/question card, and ticker all update live.

## Files

- `Playout_Display.html` — the OBS Browser Source (the overlay).
- `Playout_Control.html` — the producer control page.

Transport is Firebase Realtime Database (shared house project). State lives at `podcast/<topic>/state`; the Display subscribes, the Control publishes.
