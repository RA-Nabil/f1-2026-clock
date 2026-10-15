# 🏁 F1 2026 Clock

A minimalist, single-file website for following the 2026 Formula 1 season: a live countdown to the next race, session times in your own timezone, standings, results, teams, drivers and highlights.

No build step, no dependencies, no backend. Open `index.html` and it works.

> **Unofficial fan project.** Not affiliated with, endorsed by or connected to Formula 1, the FIA or any team. F1, Formula 1 and related marks belong to their owners.

## Features

- **Live countdown** to the next race (days, hours, minutes, seconds) with a progress ring and animated digits
- **Race weekend sessions:** Practice 1–3, Qualifying and Race for every remaining round, with Done / Live / Next status
- **Pick a race:** switch the countdown and sessions to any remaining round
- **Add to calendar:** Google Calendar links for the race and each session
- **Reminders:** an alert 15 minutes before each session (only while the page is open)
- **Time settings:** your time, track time or UTC; 12 h or 24 h (saved in your browser)
- **Results:** winner, podium and fastest lap for every completed round
- **Standings:** drivers and constructors, with animated points bars
- **Title clinch calculator:** check whether the championship can be decided at the next race
- **Teams and drivers:** base, power unit, numbers, wins, podiums, points finishes, plus driver search
- **Highlights:** links to the official F1 channel on YouTube
- **Light and dark theme**, responsive layout, keyboard focus styles, reduced-motion support

## Quick start

```bash
git clone https://github.com/<your-username>/f1-2026-clock.git
cd f1-2026-clock

# Option 1: just open the file
open index.html            # macOS (use `start` on Windows, `xdg-open` on Linux)

# Option 2: serve it locally
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy with GitHub Pages

This repo includes a workflow that publishes the site automatically on every push to `main`.

1. Push the repo to GitHub (see [docs/UPLOAD_TO_GITHUB.md](docs/UPLOAD_TO_GITHUB.md)).
2. Go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **GitHub Actions**.
4. Push a commit (or run the workflow from the **Actions** tab). Your site will be at `https://<your-username>.github.io/f1-2026-clock/`.

## Project structure

```
f1-2026-clock/
├── index.html                    # the whole site (HTML + CSS + JS)
├── README.md
├── LICENSE
├── .gitignore
├── .github/workflows/pages.yml   # GitHub Pages deployment
└── docs/
    ├── UPDATING.md               # how to refresh data after each race
    └── UPLOAD_TO_GITHUB.md       # step-by-step upload guide
```

## Keeping the data fresh

The site does **not** fetch live data. The countdown, clock and session status are calculated in your browser from the dates stored in `index.html`, but standings, results, driver notes and highlights are a snapshot (currently after the **2026 Singapore GP**, round 17). After each race, update the data arrays in the `<script>` block. See [docs/UPDATING.md](docs/UPDATING.md) for the exact steps.

## Data sources

Session times, results and standings were compiled from official and public sources, including formula1.com, crash.net, the-race.com and lightsoutblog.com. Race times are shown in UTC internally and converted for display. Schedules can change, so check formula1.com for late updates.

## Known limitations

- No live data feed (a static page can't call most third-party APIs without a backend)
- No team logos or driver photos (they are trademarked or copyrighted); badges and driver codes are used instead
- No weather forecast
- Reminders need the page open; browser notifications need your permission
- Flag emoji may appear as letters on some Windows computers

## Contributing

Corrections to schedule times, results or standings are welcome. Open an issue or a pull request with a link to your source.

## License

[MIT](LICENSE) for the code. This license does not cover Formula 1 trademarks, names or logos.
