# UNO Online

A responsive browser-based Classic UNO-style game using HTML, CSS, JavaScript, and Supabase Realtime for room broadcasts.

## Files

- `index.html` — app layout, lobby, game table, chat, scores, themes, dialogs
- `styles.css` — responsive styling
- `app.js` — deck, rules, turns, rooms, chat, and Realtime broadcasts
- `supabase-setup.sql` — setup notes for the Supabase prototype

## Run locally

Open `index.html` in a browser. For the best experience, use a local static server (for example, VS Code Live Server). The UNO Online Supabase project URL and publishable key are preconfigured, so online rooms should connect without manual setup. The gear icon can override those settings. If Realtime is unavailable, check the browser console and project Realtime settings.

## Set up online play

1. Open UNO Online; its Supabase project URL and public publishable key are already configured.
2. Create a room and share the six-character room code with friends using the same site.
3. Keep the host's browser open while playing.
4. If you want to use a different Supabase project, open the gear icon and enter that project's URL and public publishable/anon key. Never use a service-role or secret key in the browser.

The prototype uses Realtime Broadcast channels and does not need database tables. Supabase project/channel policies may need to allow the broadcast use configured for your project.

## Shareable game URLs

Room links follow `/UNO-Online/<GAMEPIN>/<NICKNAME>`, for example `https://b3434474-art.github.io/UNO-Online/ABC234/Ben`. Opening a link that includes both the six-character PIN and a nickname attempts to join that room automatically. The **Copy invite** button copies the room URL without a nickname so each friend can choose their own nickname. GitHub Pages uses `404.html` to serve the app on these room-specific paths.

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