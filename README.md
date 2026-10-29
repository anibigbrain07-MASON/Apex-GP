# Apex GP — Integrated AI + Track/Pit Bug-Fix Build

This release merges the supplied Apex GP autonomous-driving implementation with the audited 24-track routes and the realistic pit-lane/garage work. It also includes a static bug-fix pass.

## Included fixes
- Full-field randomized grid in every driving mode; no P1–P6 advantage for Race Assist.
- Rival skill variation is independent of grid slot.
- Normalized baseline vehicle power, mass, drag, braking, downforce, grip and ERS accounting so the player does not receive hidden physics multipliers.
- AI pit entry state requires physical pit-lane entry; pit-box service requires longitudinal, lateral and heading alignment. Missed boxes/entries are handled without chasing the box across the circuit.
- Automatic stuck recovery now attempts low-speed steering-based recovery rather than moving the car by rewriting its position. The manual `R` reset remains intentionally available.
- Finished cars continue at controlled cool-down pace while the field finishes; finished laps do not change the classification. The classification waits for everyone or a 90-second post-finish grace limit, then marks remaining cars DNF.
- DNF drivers score zero championship points; the season summary does not claim an all-DNF event has a winner.
- Pause menu has Resume, Return to Home, and End Race · Show Results actions.
- Preserves 24 individual waypoint routes, pit complex, team garage and setup controls.

## Run locally
1. Extract this ZIP.
2. Open `index.html` in a desktop browser.
3. Keep an internet connection enabled: Three.js and the Barlow Condensed font load from CDNs. A second Three.js CDN is attempted if the first one fails.

## Publish on GitHub Pages
Upload/replace `index.html` and `README.md` at the repository root, then use Settings → Pages → Deploy from a branch → `main` → `/ (root)`.

## Verification caveats
The inline JavaScript passed `node --check`. Static analysis found no unresolved internal identifiers; `THREE` is an intentionally external global supplied by the CDN. All 24 sampled centripetal route splines are closed and non-self-intersecting in a 1,000-sample-per-track geometry check. Automated checks do not replace a live browser race: pit service, collisions, weather, UI interaction and race finishing still need in-game testing.
