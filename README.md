# Apex GP

A browser-based racing simulator. The site entry point is `index.html`.

## Publish with GitHub Pages
1. Create a GitHub repository and upload `index.html` to the repository root.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. Wait for GitHub Pages to publish the site.

## Notes
- The game uses Three.js from a CDN, so visitors need an internet connection for the 3D engine and Google Fonts.
- This public build hides AI-training and knowledge import/export controls. Learned per-track driving parameters from the supplied knowledge pack are bundled as defaults. Local profiles already saved in the same browser take precedence.
- Race Assist and pit strategy are heuristic game AI, not a guarantee of mistake-free driving. Test the published build on desktop Chrome and mobile browsers before sharing widely.
