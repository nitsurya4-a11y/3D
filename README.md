# VOIDBORN — Browser Combat Prototype

A lightweight, playable 3D combat prototype for the VOIDBORN action RPG concept. It uses Three.js from a CDN and needs no build step.

## Run locally

```bash
python3 -m http.server 4173 --bind 127.0.0.1
```

Open `http://127.0.0.1:4173` in a modern browser. A server is necessary because the game loads JavaScript as an ES module.

## Controls

| Desktop | Action |
| --- | --- |
| WASD / Arrow keys | Move |
| J | Light attack |
| K | Heavy attack |
| Space | Dodge / Void Dash |
| Q | Phantom Strike |
| Tab | Lock nearest enemy |
| Pause button | Pause / resume |

On touch devices, use the left virtual stick and the Dash, Heavy, Void, and Attack buttons on the right.

## Android Chrome

1. Serve this directory from a machine reachable by the phone (replace `127.0.0.1` with that machine's LAN address, for example `http://192.168.1.20:4173`).
2. Connect the phone to the same network and open that address in Chrome.
3. Select a Voidbound character and press **Enter the Temple**.

The prototype targets five escalating enemy waves. Defeating wave five produces a victory screen; losing all health produces a restart screen.

## Runtime note

The Three.js ESM module is loaded from jsDelivr. Android Chrome therefore needs normal internet access the first time it loads the game.

## GitHub Pages deployment

Pushing to `main` or `master` runs the repository's GitHub Pages workflow. In the repository settings, set **Pages → Build and deployment → Source** to **GitHub Actions** once. The site uses relative `styles.css` and `game.js` paths, so it works when GitHub Pages serves it from a project subpath.

After the first successful deployment, GitHub exposes the canonical URL in the workflow's **Deploy to GitHub Pages** step. For a project site it is normally `https://<github-owner>.github.io/<repository-name>/`; replace the placeholders with the repository owner and name.
