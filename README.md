# UNO Online

A responsive browser-based Classic UNO-style game using HTML, CSS, JavaScript, and Supabase Realtime for room broadcasts.

## Files

- `index.html` — app layout, lobby, game table, chat, scores, themes, dialogs
- `styles.css` — responsive styling
- `app.js` — deck, rules, turns, rooms, chat, and Realtime broadcasts
- `supabase-setup.sql` — setup notes for the Supabase prototype

## Run locally

Open `index.html` in a browser. For the best experience, use a local static server (for example, VS Code Live Server). Without Supabase credentials the app opens a local demo room; online rooms require Supabase.

## Set up online play

1. Create a free project at [Supabase](https://supabase.com/dashboard).
2. Open UNO Online and click the gear icon.
3. Paste your Supabase **Project URL** and public **anon/publishable key**. Never use a service-role or secret key in a browser.
4. Save settings.
5. Create a room. Share the six-character room code with friends who also have the deployed site and the same Supabase project settings.
6. Keep the host's browser open while playing.

The prototype uses Realtime Broadcast channels and does not need database tables. Supabase project/channel policies may need to allow the broadcast use configured for your project.

## Publish free with GitHub Pages

1. Open this repository on GitHub.
2. Go to **Settings → Pages**.
3. Under Build and deployment, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then save.
5. Wait for GitHub Pages to finish and open the URL it provides.

No build step is required.

## Current prototype limits

- A room host browser coordinates the game and must stay connected.
- Realtime broadcasts are not a secure game server; clients may inspect shared state. Use this for casual games with people you know.
- Chat is room-scoped by channel but is not designed for private or sensitive messages.
- Scores are stored in each player's browser, not in a global leaderboard.
- The UNO call button is included, but missed-call penalties and full official challenge handling are not implemented.
- This is an independent fan project and is not affiliated with or endorsed by Mattel. UNO is a trademark of its respective owner.

## Rules

Matching color, number, or symbol; Skip, Reverse, Draw Two, Wild, and Wild Draw Four; seven cards per player. Wild Draw Four checks that the player has no card matching the current color. First player to empty their hand wins.