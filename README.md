# Pacificon App Data

Live conference data for the Pacificon companion app. The app fetches
`sessions.json` and `speakers.json` from this repo's raw URLs on launch and
when it returns to the foreground, so edits here reach attendees' phones
within a couple of minutes — no app-store release needed.

## Editing rules

- Keep JSON valid — a malformed file is ignored by the app (it keeps its
  last good copy), so nothing breaks, but your change won't appear.
- **Never change or reuse an existing session's `id`** — attendees' favorites
  are stored by session id on their phones.
- Speaker `photoUri` may be a full URL; photos in `photos/` are served at
  `https://raw.githubusercontent.com/anton1s/pacificon-data/main/photos/<file>`.
- Don't add email addresses or other private contact info — this repo is public.
