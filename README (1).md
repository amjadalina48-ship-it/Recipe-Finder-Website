# The Recipe Box 🥕🍅

A single-page recipe finder website with a farm-stand kitchen look — login/register, six recipe categories styled as wooden crates, and recipe details shown on a chalkboard.

## What's inside

- **`recipe-finder.html`** — the entire website (HTML, CSS, and JavaScript) in one file. Open it directly in any browser, no server or build step required.

## How it works

1. **Sign in or register** — a seed-packet-style card lets a visitor log in or create an account.
2. **Pick a category** — six wooden crates: Breakfast, Lunch, Dinner, Snacks, Desserts, Drinks.
3. **Browse recipes** — each category opens a grid of recipe cards (15 recipes per category, 90 total).
4. **View a recipe** — tapping a card opens a chalkboard-style detail view with the full ingredient list and numbered steps.

## Demo login

| Email | Password |
|---|---|
| `demo@cook.com` | `cook123` |

Or register a brand-new account from the sign-in screen — no demo login required.

## Important: accounts are not saved permanently

This is a **static, front-end-only** site. There is no database or server behind it, so:

- Accounts created via "Register" only exist in the browser's memory for that session.
- **Refreshing the page, or closing the tab, erases any accounts you registered** (the built-in demo account always comes back, since it's hard-coded into the page).
- No real password security, encryption, or validation is applied — this is a design/demo prototype, not a production login system.

If you want accounts and logins to persist for real (so users can come back days later and still be signed in), that requires a real backend and database. Options include:
- A simple backend (Node/Express, Python/Flask, etc.) with a database (SQLite, Postgres, MongoDB)
- A backend-as-a-service (Firebase, Supabase, Auth0) for authentication + storage

I'm happy to help build one of these out if you'd like to take the project further.

## Customizing the recipes

All recipe data lives near the top of the `<script>` section in `recipe-finder.html`, inside the `RECIPES` object — organized by category, with each recipe as:

```js
{ name: 'Recipe Name', blurb: 'Short one-line description.',
  ingredients: ['...', '...'],
  steps: ['...', '...'] }
```

Add, remove, or edit recipes by editing this object directly — no other code needs to change. The category "crate" on the home screen will automatically update its recipe count.

## Customizing the look

Colors, fonts, and shapes are controlled by CSS variables at the top of the `<style>` section (e.g. `--leaf`, `--tomato`, `--carrot`, `--wood`). Change these to shift the whole palette without touching the layout.

Fonts used:
- **Permanent Marker** (Google Fonts) — chalkboard-style headings
- **Nunito** (Google Fonts) — body text and UI

Both are loaded via a `<link>` tag, so an internet connection is needed the first time the page loads fonts (they're cached after that).
