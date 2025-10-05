# Clifford • Attestations (public)
Sanitized, consented attestations from the Clifford kiosk.

- `index.json` — list of entries (id, ts, name, text, sha256, relpath)
- `attestations/<YYYY>/<ID>/` — per-entry folder with:
  - `meta.json` (public subset)
  - `receipt.txt`
  - optional `photo.jpg|png`, `audio.webm`
