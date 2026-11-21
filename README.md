# LeadTrack – Videos tab (Gzami 7.8)

A YouTube-style video browser and player inside the LeadTrack offline app (`Gzami_7.8_Videos.html`).
Search and browse use the YouTube Data API v3. Playback uses YouTube's embedded IFrame player, so you stay in the app.

## Setup

1. Go to https://console.cloud.google.com and create or pick a project.
2. Enable **YouTube Data API v3**.
3. Credentials → **Create credentials → API key**.
4. Restrict the key to **YouTube Data API v3** only.
5. Open the **Videos** tab in the app, paste the key and tap **Save & start**.

The key is stored only in this browser (`localStorage`, key `leadtrack_yt_key`).
To pre-fill it for everyone using the file, set `DEFAULT_KEY` at the top of the `<script id="yt-player">` block.

## Features

- Home grid with chips: Trending, Cruises, Cordelia Cruises, Travel, Music, News, Sales & business, Live, Gaming, New
- Search box. Pasting a YouTube link opens that video directly
- Infinite scroll
- Watch page: player, description (clickable timestamps), comments, "Up next", likes and subscribers
- Theater mode and autoplay-next
- Mini player docked bottom-right when you scroll away or change tabs
- Resume from where you stopped
- Library: Watch history and Watch later
- Settings: API key, region, safe search, clear data

## Keyboard shortcuts (watch page)

| Key | Action |
|---|---|
| K / Space | Play / pause |
| J / L | Back / forward 10 s |
| ← / → | Back / forward 5 s |
| M | Mute |
| F | Fullscreen |
| T | Theater mode |
| N | Next video |
| 0–9 | Jump to 0–90% |
| < / > | Playback speed |

## Limits and notes

- **Opened from disk (`file://`):** YouTube may block the embedded player (Error 153). The app then shows an "Open on YouTube" button. Hosting the file on any http(s) site avoids this.
- Videos whose owners disabled embedding can only be played on YouTube.
- Quota: free tier is 10,000 units per day. A search costs 100 units, so about 100 searches a day. Video, channel and comment lookups cost about 1 unit each.
- Needs an internet connection. Results are cached for 30 minutes.
- Hover preview is disabled on `file://` and touch devices.

## Stored data (localStorage)

`leadtrack_yt_key`, `leadtrack_yt_hist`, `leadtrack_yt_later`, `leadtrack_yt_prog`, `leadtrack_yt_set`, `leadtrack_yt_recent`, `leadtrack_yt_av`
