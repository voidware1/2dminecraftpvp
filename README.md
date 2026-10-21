# Voidware 2D Minecraft PvP

## Files
- `index.html` — main play menu
- `play.html` — Firebase sign-in, 1v1/2v2 queue-entry UI, private rooms (up to 16 players), host team assignment
- `game.html` — arena placeholder for wiring in the actual combat engine

## GitHub Pages setup
1. Upload these files to the root of `voidware1/2dminecraftpvp`.
2. In GitHub, open **Settings → Pages** and publish from the `main` branch, root folder.
3. The site URL will usually be `https://voidware1.github.io/2dminecraftpvp/`.

## Firebase setup
In Firebase Console for project `bedwars-2f641`:
1. Authentication → Sign-in method → enable **Anonymous**.
2. Realtime Database → create/confirm the database at `https://bedwars-2f641-default-rtdb.firebaseio.com/`.
3. Configure and test database rules before using this publicly. Do not set the whole database to public read/write.
4. Add GitHub Pages domain to Authentication → Settings → Authorized domains if needed.

## Important prototype limitations
- `play.html` writes queue entries but does not yet have a trusted matchmaking service to pair users and create authoritative matches.
- Private-room lobby writes and team assignment are client-side scaffolding. Production use needs rules that enforce host-only team changes, membership, room capacity, and allowed status transitions.
- `game.html` is a placeholder. Actual combat, projectiles, collision, inventory, bot AI, and authoritative online match state still need to be integrated.
- Firebase web config (including API key) is client-visible by design; protect data with Authentication and security rules.
