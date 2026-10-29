# Garden Bird Survey Dashboard

An interactive dashboard for exploring 10-minute Merlin Sound ID bird surveys from a back garden in Selwyn, Canterbury, New Zealand. Please note Merlin Sound ID records what it detects acoustically, not necessarily every bird physically present in the garden. Background noise and detection accuracy can affect the results

This is an improved single-file prototype that builds on the original [garden-birds](https://github.com/mvanenter/garden-birds) project.

## Features

- Live data loading from a published Google Sheet (with fallback sample data)
- Interactive filters: time of day, noise, wind, rain, species, session date
- Summary KPIs: sessions, species count, mean richness, latest richness, total rain
- Charts: richness by date / start time / wind, detection frequency, rainfall
- Species-by-session presence matrix
- Species guide with photos, scientific names, status (native/introduced), short descriptions, and Wikipedia links
- Click a species card or a date bar to filter the whole dashboard
- Light / dark theme
- Incidental observations kept separate from formal counts

## How to run

1. Place `index.html` and `garden-bg.svg` in the same folder.
2. Open `index.html` in a modern browser  
   **or** serve the folder locally, e.g.:
   ```bash
   python3 -m http.server 8000
   ```
3. An internet connection is needed for Chart.js (CDN), Wikipedia photos, and the live spreadsheet.

No build step is required.

## Data source

The dashboard reads a published Google Sheets CSV.  
To use your own data, edit the `SHEET_CSV_URL` constant near the top of the `<script>` block in `index.html`.

Expected columns (header names matter):

| Column              | Example          | Notes                          |
|---------------------|------------------|--------------------------------|
| Session_ID          | S001             | Optional (auto-generated)      |
| Date                | 20/10 or 20/10/2026 | Required                    |
| Start_Time          | 9:40 or 9:40 am  | Required                       |
| End_Time            | 9:50 AM          | Shown under time of day        |
| Birds_Recorded      | Blackbird, House Sparrow | Required (comma/semicolon separated) |
| Wind_Kmh            | 22               |                                |
| Background_Noise    | Low / Medium / High | Filter + table              |
| Time_of_Day         | Early morning    |                                |
| Wind_Direction      | N, NNW, SE…      |                                |
| Weather_Condition   | Sunny, Overcast  | Conditions table               |
| Cloud_Cover_Pct     | 37               | Conditions table               |
| Rain_mm             | 0 or 4.1         | Use 0 for dry                  |
| Rain_Chance_Pct     | 45 or 45%        |                                |
| Humidity_Pct        | 65               | Conditions table               |
| Temperature_C       | 16               |                                |
| Notes               | free text        | Session notes section          |

Merlin detections are treated as identification records, not independently verified presence.  
Incidental sightings (outside the formal 10-minute counts) are listed separately and excluded from richness calculations.

## Project status

Prototype. The current live sheet contains the first survey sessions (from 20 Oct 2026 onward).  
The sample is still small — treat patterns as exploratory, not definitive.

## Planned improvements

- Sunrise / sunset integration (Open-Meteo)
- Automated environmental data join (FME or similar)
- Bird call links
- More temporal and environmental comparisons
- Optional GIS layer

## Credits

- Bird photos and metadata via Wikipedia / Wikimedia Commons APIs
- Chart.js for visualisations
- Original concept and data collection by [mvanenter](https://github.com/mvanenter)
