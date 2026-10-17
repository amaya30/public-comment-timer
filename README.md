# Public Comment Timer

A simple, large-display countdown timer for the public comment period of city council meetings. A clerk or chair starts the clock when a speaker begins, and the speaker and the room can see how much time remains.

## Features

- Giant minutes:seconds countdown readable from across a chamber
- Status label (Ready, Speaking, Wrap up, Paused, Time) and a progress bar
- Clock turns amber at 30 seconds remaining and red at zero
- Adjustable time limit (default 2:00) with 1:00, 2:00 and 3:00 presets; the limit is remembered between visits
- The limit can only be changed while the timer is reset, so it can't be altered mid-speaker
- Keeps the screen awake while running, where the browser supports it
- Light and dark modes follow the system setting
- Colors and fonts echo the City of Cheney website
- Works offline once loaded, and can be installed as an app (see [Offline use](#offline-use))

## Usage

Use the live timer at https://publiccommenttimer.org, or open `index.html` in a browser. There is no build step, so it can be hosted on any static web host.

### Offline use

Fonts are self-hosted and a service worker caches the app, so after one visit over HTTPS it works with no network, and it can be installed to the home screen or desktop. Service workers don't run from `file://`, so opening the file directly works but won't be cached. Host all the files together (`index.html`, `sw.js`, `manifest.webmanifest`, `icon.svg`, `fonts/`). When you change any of them, bump `CACHE` in `sw.js` so installed copies update.

### Controls

| Control | Action |
| --- | --- |
| Start / Pause / Resume button, or `Space` | Start, pause or resume the countdown |
| Reset button, or `R` | Return the clock to the full time limit |
| Minutes / Seconds fields, or preset buttons | Set the time limit (only while reset) |

## Deployment

The site is hosted on GitHub Pages from the `main` branch (root folder) and served at `publiccommenttimer.org`. Pushing to `main` redeploys it within a minute or two. The `CNAME` file sets the custom domain and should not be removed. DNS uses GitHub's four `A` records on the apex domain and a `www` CNAME to `amaya30.github.io`.

This is an independent tool and is not run by the City of Cheney.
