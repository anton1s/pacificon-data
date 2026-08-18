# Pacificon App Data

Live conference data for the Pacificon companion app. The app fetches
`sessions.json`, `speakers.json`, `vendors.json` and `organizers.json` from
this repo's raw URLs on launch and
when it returns to the foreground, so edits here reach attendees' phones
within about 5 minutes (GitHub's CDN cache) — no app-store release needed.

## Editing rules

- Keep JSON valid — a malformed file is ignored by the app (it keeps its
  last good copy), so nothing breaks, but your change won't appear.
- **Never change or reuse an existing session's `id`** — attendees' favorites
  are stored by session id on their phones.
- Speaker `photoUri` may be a full URL; photos in `photos/` are served at
  `https://raw.githubusercontent.com/anton1s/pacificon-data/main/photos/<file>`.
- Speaker photos: drop `photos/<speaker id>.jpg` (or `.png`) here and the app
  picks it up automatically for speakers without a bundled photo.
- `organizers.json`: one entry per role (`id`, `name`, `role`, optional
  `callsign`, `email` or `website`, `hidden`). Only use public role
  addresses (chair@pacificon.org etc.) here — this repo is public.
- Don't add other email addresses or private contact info — this repo is public.
