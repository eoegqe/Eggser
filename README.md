# Eggser Control Center

A browser-based control panel for **Eggser (Bedrock)**, branded for Theegget Creations.

## Live integrations

The panel connects to the protected Cloudflare Worker at `https://eggser-api.theegget.com`.

- Live server status and online player names from Exaroton
- Server start, stop, and restart requests
- Live editable options exposed through Exaroton's `server.properties` configuration API
- Kick commands sent to the server through Exaroton's command API
- Search and filtering for live settings and online players

Some setting changes require a server restart. Management requests require the `EGGSER_CONTROL_TOKEN` secret to be configured on the `eggser-api` Worker and the matching token to be entered in the panel. The Exaroton API token must remain a Worker secret and must never be placed in browser code.

## Preview-only sections

These sections are not yet connected to live world data:

- Inventory editor
- Ender Chest editor
- Player map and coordinates
- Item kit previews
- Offline-player history and bans

These areas use preview/sample data and do not modify the actual world.

## API endpoints used by the panel

- `GET /server` — server status and player list
- `POST /server/start`, `POST /server/stop`, `POST /server/restart` — power controls
- `GET /world/settings` — read editable `server.properties` options
- `POST /world/settings` — save validated server settings
- `POST /players/kick` — kick an online player with a reason

All management POST requests require `X-Eggser-Control-Token`. The Worker validates settings against the options returned by Exaroton and validates player names before issuing kick commands.

## Hosting

Open `index.html` in a browser or use GitHub Pages / the configured site deployment for the panel. Keep the Exaroton API token and control token in Cloudflare Worker secrets. GitHub Pages serves the front end only; it cannot securely store these secrets or run the API backend.
