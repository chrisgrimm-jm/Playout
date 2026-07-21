# Playout

A title bar maker for podcasts. Design one branded lower-third title bar, drive it live as an OBS overlay, or export it as a transparent PNG to drop into an edit.

- **Title bar** — title + optional subtitle, in the Jomboy lower-third style (navy box, red spine, italic Bebas title, mono red subtitle). Drag to position, slider to resize.
- **Live OBS overlay** — one Browser Source, synced from the control page over Firebase (no server, no refresh on air).
- **PNG export** — full 1920×1080 transparent frame (placed exactly where it sits on the overlay) or a snug crop around the bar.
- **Presets** — save recurring titles as one-click buttons.

Branded to the Jomboy Media design system: Bebas Neue + DM Mono, red `#E40000`, navy surfaces.

## Use — live overlay

1. Open **`Playout_Control.html`** in a browser (producer's machine).
2. Set a **Topic** (channel) at the bottom so only you can post.
3. Copy the **OBS Browser Source URL** and add it as one Browser Source in OBS at **1920×1080**.
4. Type a title (and optional subtitle), position/size it, hit **SHOW ON SCREEN** — it updates live.

## Use — export a PNG

1. Set the title, subtitle, position, and size on the control page.
2. Hit **EXPORT 1920×1080** for a full-frame transparent PNG, or **Cropped to bar** for a snug transparent PNG of just the bar.

## Files

- `Playout_Display.html` — the OBS Browser Source (the overlay).
- `Playout_Control.html` — the control page (design, drive live, export PNG).

Transport is Firebase Realtime Database (shared house project). State lives at `podcast/<topic>/state`; the Display subscribes, the Control publishes.
