# Apex GP — Bug-Fixed GitHub Pages Build

This package contains the Apex GP browser racing game. Keep `index.html` and this `README.md` in the repository root.

## Publish with GitHub Pages

1. Extract the ZIP file.
2. Upload `index.html` and `README.md` to the root of your GitHub repository (not inside another folder).
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch **main** and folder **/(root)**, then save.

## Included fixes

- The pause key ignores key-repeat events, preventing a held `P` key from rapidly pausing and resuming.
- The next race avoids the player's immediately previous grid slot while keeping all grid slots available over time.
- CSV and JSON telemetry export uses the browser's native Blob download support instead of a host-specific download API.
- A player who runs out of fuel and remains nearly stationary for eight seconds is retired as a DNF. The race then receives a 45-second classification grace period; DNFs are placed behind classified finishers and score zero championship points.
- Previously saved driving-assist selections are preserved when loading the updated version. Fresh installations still default to Autonomous Race Assist.
- Touch-screen controls are provided for left/right steering, braking, throttle and ERS.
- Mobile and Chromebook profiles start with antialiasing disabled. Switching between Powerful and a lightweight profile requires a page reload for the antialiasing change to take effect.

## Controls

- Arrow keys: steer / throttle (Up) as applicable to the selected driving mode
- Space: brake
- E: ERS boost
- A: toggle Race Assist; double-tap A for full manual control
- P: pause / resume
- C: change camera
- R: reset car
- X: request / cancel a pit stop
- 1–5: select tyre compound

Touch devices also show on-screen steering, brake, throttle and ERS buttons during races.

## Browser storage and network notes

- Three.js r128 is loaded from a CDN (with a fallback CDN). A network connection is required when the library is not already cached. The game engine is not bundled locally in this ZIP.
- Driver settings, championship progress, previous grid position and best-lap data are saved in the current browser's local storage. This is per-browser/per-device storage, not a cross-player online leaderboard.
- Google Fonts is optional; the game has system-font fallbacks.

## Testing notes

The inline JavaScript passed `node --check`; static checks found no duplicate HTML IDs, and the ZIP integrity test passed. The race systems still need a real browser run to validate live physics, AI traffic, pit stops, weather and championship flow. These checks are not a substitute for a full in-browser race test.
