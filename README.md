# News Wall

A lightweight, single-page dashboard for watching multiple live international news channels simultaneously in a configurable grid layout. No installation, no build step — just open and watch.

## Features

- **Multiple layouts** — choose from `2x2`, `2x3`, `3x3`, `4x3`, or `1plus` (focus view)
- **Per-panel mute controls** — independently mute any panel
- **Global mute** — mute all panels at once via the `Mute All` button or press `M`
- **Closed caption support** — auto-detected and shown as top-positioned overlays when available
- **Fallback streams** — multiple URLs per channel for resilience when a stream goes down
- **Zero dependencies** — only `hls.js` (loaded from CDN) for HLS playback in non-Safari browsers
- **Dark theme** — clean, focused UI

## Channels

| Channel | Region |
|---|---|
| Global News | Canada |
| Al Jazeera | Qatar / International |
| MSNBC Now | USA |
| Bloomberg | USA / International |
| France 24 | France / International |
| DW News | Germany / International |
| TRT World | Turkey / International |
| NHK World | Japan / International |
| Euronews | Europe |
| WION | India / International |
| Arirang | South Korea / International |
| NDTV 24x7 | India |

> **Note:** Stream URLs point to live HLS feeds that can change or go offline without notice. If a channel stops working, the stream URL likely needs updating.

## Getting Started

This project is a single static HTML file. No build step or package installation is needed — just serve it with any local HTTP server.

### Python

```bash
python3 -m http.server 9988
```

### Node.js

```bash
npx serve . -l 9988
```

Then open [http://localhost:9988](http://localhost:9988) in your browser.

## Browser Compatibility

| Browser | HLS Playback |
|---|---|
| Safari | Native HLS support |
| Chrome, Firefox, Edge | Via `hls.js` (CDN) |

## Project Structure

```
news-wall/
└── index.html   # The entire app — markup, styles, stream config, and logic
```

## Contributing

Contributions are welcome. Some useful things to improve:

- Updated or additional stream URLs when channels change
- New channel sources
- Layout or UI improvements
- Bug fixes

Please open an issue before submitting a large change, so we can discuss the approach first.

## Stream Reliability

Live stream URLs are sourced from public HLS feeds and can break when:

- A broadcaster changes or removes their stream URL
- A CDN endpoint goes down or requires authentication
- Geographic restrictions prevent access

If a channel shows a black screen or error, try refreshing. If it persists, the stream URL may need to be updated in `index.html`.

## License

[MIT](LICENSE) — free to use, modify, and distribute.

If you build something with this project, a link back to [github.com/rkenedi/news-wall](https://github.com/rkenedi/news-wall) is appreciated (though not required).
