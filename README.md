<div align="center">

# WarHeatMap · Live

**The live window into [warheatmap.app](https://warheatmap.app): a world record of conflict events where every event carries a cited source.**

[![live build](https://github.com/indicaindependent/warheatmap-live/actions/workflows/live.yml/badge.svg)](https://github.com/indicaindependent/warheatmap-live/actions/workflows/live.yml)

**[Open the mini map](https://indicaindependent.github.io/warheatmap-live/)** · **[Open the full map](https://warheatmap.app)** · **[Talk](https://warheatmap.app/Talk)**

</div>

Everything below is live. The cards and the map are rebuilt about every 30 minutes from the public
warheatmap.app feed and served from this repository's GitHub Pages site, so this page always shows
the current picture without a click. Select any image to open the interactive mini map.

---

## Right now

<a href="https://indicaindependent.github.io/warheatmap-live/"><img src="https://indicaindependent.github.io/warheatmap-live/live-card.svg" alt="WarHeatMap live status, rebuilt about every 30 minutes from the public warheatmap.app feed: events in the last 24 hours and 7 days, countries covered, severity mix, and the five newest events with their sources." width="100%"></a>

## The last 7 days

<a href="https://indicaindependent.github.io/warheatmap-live/"><img src="https://indicaindependent.github.io/warheatmap-live/live-map.svg" alt="The last 7 days of WarHeatMap events plotted on a world map and coloured by severity: critical, high, medium, low." width="100%"></a>

| Severity | Colour | Dot size |
|:---|:---|:---|
| **Critical** | rose `#FB7185` | largest |
| **High** | amber `#F5A524` | large |
| **Medium** | cyan `#2DD4E8` | medium |
| **Low** | green `#4ADE80` | smallest |

## What the feed is made of

<a href="https://indicaindependent.github.io/warheatmap-live/"><img src="https://indicaindependent.github.io/warheatmap-live/live-mix.svg" alt="WarHeatMap live event mix: the newest 500 events in the public warheatmap.app feed, broken down by event type and severity, with counts of named conflicts and cited sources. Rebuilt with the live card." width="100%"></a>

---

## The mini map

GitHub pages cannot run an interactive app inside a README, so the mini map lives one click away at
**[indicaindependent.github.io/warheatmap-live](https://indicaindependent.github.io/warheatmap-live/)**.
It reads the newest 500 verified events live in your browser.

- **Filter** by time window (24 hours, 7 days, everything loaded), by severity, and by event type.
- **Select any dot or row** to see the event, its time in UTC, its severity and country, and its sources.
- **Open the event's permanent page** on warheatmap.app, so a single strike can be cited, shared and checked.

No login, no cookies, no analytics, no third-party scripts. The page runs under a strict content
security policy that lets it reach only its own site and warheatmap.app.

---

## Talk: #warheatmap

One community, two doors. Use Discord if you have it, IRC if you don't.

| Discord | IRC on EFnet |
|:---|:---|
| **[Join the Discord](https://discord.osintnet.uk/)** | **[Chat in your browser](https://chat.efnet.org/#warheatmap)**, nothing to install |
| Free account, any device | Or any IRC client: `irc.efnet.org`, port 6697 (TLS), channel `#warheatmap` |

---

## How it stays live

```
warheatmap.app public feed ──► live/build_live.py ──► GitHub Pages
  verified events only           card, map, mix,        indicaindependent.github.io/warheatmap-live
  no credentials                 status.json, mini map  refreshed about every 30 minutes
```

| File | What it does |
|:---|:---|
| [`live/build_live.py`](live/build_live.py) | Reads the public feed and writes `live-card.svg`, `live-map.svg`, `live-mix.svg`, `status.json` and the mini map page |
| [`live/index.html`](live/index.html) | The interactive mini map |
| [`live/land.json`](live/land.json) | World land outline (Natural Earth 110m) used to draw the map |
| [`.github/workflows/live.yml`](.github/workflows/live.yml) | Runs the build on a schedule and deploys it to Pages as an artifact, so refreshes add nothing to git history |

The machine-readable summary behind the card is published at
[`status.json`](https://indicaindependent.github.io/warheatmap-live/status.json).

**What this repository is not.** It holds only the live view. The WarHeatMap application itself is
not published here, and nothing in this repository can write to it.

---

<div align="center">

<sub>WarHeatMap reports on armed conflict, including deaths and injuries. Dedicated to the people of Ukraine: <a href="https://u24.gov.ua/donate/defense">donate directly through UNITED24</a>.</sub>

<sub>MIT licensed · built by <a href="https://github.com/indicaindependent">Indica Independent Media</a></sub>

</div>
