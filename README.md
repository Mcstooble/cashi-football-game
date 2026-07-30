# Cashi Football Prediction Game

Al Hilal Omdurman vs Rayon Sports · CECAFA Club Cup · Saturday 1 August 2026

A single-page prediction game. Players call the final score and the minute of
every goal. One entry per Cashi account number, locked once sent.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole game. No build step, no dependencies. |

## Running it locally

Open `index.html` in a browser. That's it.

With no Supabase keys set it runs in **preview mode** — every screen works and
looks real, but nothing is saved. Useful for reviewing copy and layout.

## Going live

Set the two values at the top of the `<script>` block in `index.html`:

```js
const SUPABASE_URL      = "https://xxxxxxxx.supabase.co";
const SUPABASE_ANON_KEY = "eyJ...";
```

Both are safe to commit. The `anon` key is public by design and the database is
locked with row-level security — it can only call a handful of named functions
and cannot read the entry list.

The kickoff time is also set there. Predictions lock at that moment, enforced by
the database clock rather than by the browser.

## Deployment

Static hosting. Any host, any CDN, no server required. Needs HTTPS — Supabase
rejects insecure origins.

Production domain: `football.getcashi.com`

## What is NOT in this repo

The database schema, the setup notes and the admin password are deliberately
kept out, because this repo is public. Ask Josh for them.
