# Sonora

A responsive, Apple Music-inspired **local music player for the browser**. Import your own audio files and listen with a polished library, queue, playlists, synced lyrics, and a full-screen player.

> Sonora is an independent concept project. It is not affiliated with or endorsed by Apple, and it does not stream music from Apple Music.

## Features

- Import individual audio files or an entire music folder
- Drag and drop files and folders into the player
- Local music library saved in the current browser using IndexedDB
- Album, artist, genre, songs, favorites, and recently added views
- Playlists, queue management, shuffle, repeat, and playback controls
- Reads supported embedded tags and cover art where available
- Supports external `.lrc` lyric files and embedded lyrics where available
- Light, dark, and automatic themes
- Dynamic, cover-art-inspired backgrounds and full-screen player
- Responsive desktop and mobile layouts
- Installable web app on supported browsers, with a cached app shell for repeat offline visits
- Keyboard shortcuts and media-session metadata where supported
- No framework, package install, backend, or API key required

## Run locally

This is a static, single-page app. The simplest reliable way to run it is with a local web server.

```bash
python -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000).

You can also open `index.html` directly in a modern browser, but browser storage and file APIs work more consistently when served from `localhost` or HTTPS.

## Deploy with GitHub Pages

1. Create a new GitHub repository named `sonora-music-player`.
2. Upload all project files (`index.html`, `README.md`, `.nojekyll`, `manifest.webmanifest`, `service-worker.js`, and the icon files) to the repository's root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`, then save.
6. Wait for GitHub Pages to publish the site; the URL will appear in the Pages settings.

## Deploy with Vercel

1. Push this repository to GitHub.
2. In Vercel, import the repository.
3. Choose the **Other** framework preset; no build command is needed for this static HTML project.
4. Set the output directory to `.` if Vercel asks for one, then deploy.

## Privacy and storage notes

- Sonora processes the music files you choose in your browser; it does not upload them to a Sonora server.
- Imported tracks and preferences are stored in browser-local storage (IndexedDB/localStorage) for the site origin.
- Browser storage is not a backup. Clearing site data, using a different browser/profile/device, or storage eviction may remove your library. Keep your original music files.
- Playback depends on the audio/video codecs supported by your browser.
- The app shell is cached by a service worker after the first successful online visit, so supported browsers can reopen Sonora offline. Open the site online once first; service-worker/PWA support varies by browser and hosting context.

## Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `Space` | Play / pause |
| `←` / `→` | Seek backward / forward 5 seconds |
| `Shift` + `←` / `→` | Previous / next track |
| `↑` / `↓` | Adjust volume |
| `M` | Mute |
| `S` | Shuffle |
| `R` | Repeat |
| `F` | Favorite current track |
| `L` | Lyrics |
| `Q` | Up next / queue |
| `N` | Now playing |
| `/` | Search |
| `Esc` | Close menus or full-screen player |

## Tech

HTML, CSS, and vanilla JavaScript. No build step or external runtime dependencies.
