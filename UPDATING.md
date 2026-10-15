# Updating the data after each race

All data lives in the `<script>` block at the bottom of `index.html`. Edit the arrays below, commit and push. GitHub Pages redeploys automatically.

## 1. Results (`RES`)

Add one row per completed race, in calendar order:

```js
["Singapore","🇸🇬","Oct 11","Verstappen","Leclerc","Antonelli","Leclerc"]
//  race       flag  date     winner      2nd       3rd        fastest lap
```

The round number is the row's position in the array.

## 2. Standings (`DRV` and `TEAMS`)

Both arrays are listed in championship order. Update the points and wins, and re-sort if positions changed.

```js
// DRV: [name, nationality, teamKey, wins, points, note]
["Kimi Antonelli","ITA","mer",8,340,"Short note shown on the driver card."]

// TEAMS: [key, name, base, power unit, colour, points, wins, blurb]
["mer","Mercedes","Brackley, UK","Mercedes","#27c4b0",578,11,"Short blurb."]
```

Also update `DX` (driver number, podiums, points finishes), in the same order as `DRV`.

The title clinch calculator uses the hard-coded values `340`, `238` and `229` (Antonelli, Russell and Hamilton points) and `125` (points still available) inside `calcTitle()`. Update those after every race.

Also update the footer and the note under the standings ("After round 17 of 23 · Singapore GP").

## 3. Remove the finished race from the schedule (`RACES`)

Finished races drop out automatically once their start time has passed, so no edit is needed. To add or fix a round, use this shape (all times UTC, ISO format):

```js
{r:18, n:"United States", k:"Austin", f:"🇺🇸", c:"Austin (COTA)",
 z:"America/Chicago", len:5.513, laps:56,
 t:"2026-10-25T19:00:00Z",                      // race start
 s:[["Practice 1","2026-10-23T17:30:00Z"],       // sessions
    ["Practice 2","2026-10-23T21:00:00Z"],
    ["Practice 3","2026-10-24T17:30:00Z"],
    ["Qualifying","2026-10-24T21:00:00Z"]]}
```

For a sprint weekend, add `["Sprint Qualifying", "..."]` and `["Sprint", "..."]` to `s`. The page shows "No sprint this weekend" when none is listed.

Convert local times to UTC with the track's offset (for example Austin in October is UTC−5, so 14:00 local is 19:00Z).

## 4. Highlights (`HL`)

Each item is `{k:"Race", t:"Video title"}`. Without an `id` the card opens a YouTube search for the title. Add the video ID for a direct link:

```js
{k:"Race", t:"Race Highlights: 2026 Singapore Grand Prix", id:"VIDEO_ID"}
```

## 5. Check before you push

Open `index.html` in a browser and click through every tab. In the browser console there should be no errors.
