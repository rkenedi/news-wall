# News Wall

`News Wall` is a lightweight single-page dashboard for watching multiple live news channels at once in a configurable grid.

It is built as a static HTML file with:

- `hls.js` for HLS playback in browsers that do not support HLS natively
- Multiple preset layouts including `2x2`, `2x3`, `3x3`, `4x3`, and `1plus`
- Per-panel mute controls
- A global `Mute All` action
- Caption detection and top-positioned caption overlays when tracks are available
- Fallback stream URLs for some channels

## Project Structure

- `index.html` - the entire app, including markup, styles, stream configuration, and client-side logic

## Run Locally

This project does not need a build step or package install. It just needs to be served as static files from a local web server.

### Option 1: Python

From the project directory:

```bash
python3 -m http.server 9988
```

Then open:

```text
http://localhost:9988
```

### Option 2: Node.js

If you prefer a Node-based static server:

```bash
npx serve . -l 9988
```

Then open:

```text
http://localhost:9988
```

## Notes

- Some streams may fail or change over time; several sources include fallback URLs.
- Closed captions depend on whether the upstream stream exposes text tracks.
- Safari can use native HLS support; other modern browsers rely on the included `hls.js` CDN script.
