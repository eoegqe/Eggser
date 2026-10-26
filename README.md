# Eggser Control Center

A no-code-style, browser-based control panel prototype for Eggser (Bedrock), branded for Theegget Creations.

## Current prototype

Open `index.html` in a browser or enable GitHub Pages for this repository.

Included UI sections:
- Server overview and power-control placeholders
- Player list and search
- Inventory slot editor (main inventory, hotbar, armor/offhand)
- Ender Chest slot editor
- Player map canvas with sample markers
- Searchable no-code configuration controls
- Item kit previews
- Local activity log

## Important status

This is currently a **front-end prototype**. It uses sample data and local in-page state. It does not yet connect to Exaroton or modify a live Minecraft server. All controls explicitly indicate preview-only behavior.

## Integration needed for live management

1. Add a server-side backend for Exaroton API calls. Store the Exaroton API token as a backend secret; never put it in browser JavaScript.
2. Connect a compatible Bedrock server-side bridge/plugin/add-on for player data, inventory and Ender Chest access, commands, and live coordinates.
3. Connect a world-map provider or generate a map from supported server-side world data.
4. Add owner authentication and server-side authorization to every management endpoint before enabling destructive actions.
5. Confirm which Exaroton-hosted Bedrock server software is being used, since inventory and map integration options depend on it.

## Hosting on GitHub Pages

In the repository settings, open **Pages**, choose the `main` branch and `/(root)`, then save. This serves the static preview only. GitHub Pages cannot securely store an Exaroton API token or run a private API backend.
