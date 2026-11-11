# WarHeatMap live

The live status card, 7-day map, event mix and mini map for [warheatmap.app](https://warheatmap.app), rebuilt about every 30 minutes and published at **https://indicaindependent.github.io/warheatmap-live/**.

Everything here is built from warheatmap.app's **public** event feed. No credentials are used or needed. This repository holds only the live card builder; the WarHeatMap application itself is not published.

| File | What it is |
|---|---|
| `live/build_live.py` | Reads the public feed and writes `live-card.svg`, `live-map.svg`, `live-mix.svg`, `status.json` and the mini map page |
| `live/index.html` | The mini map: filter by severity and event type, open any event and its source |
| `live/land.json` | World land outlines used to draw the map |
| `.github/workflows/live.yml` | Runs the build about every 30 minutes and deploys it to GitHub Pages, without committing |

MIT licensed.
