# Garden Bird Survey Dashboard

An interactive dashboard exploring bird observations from my back garden in Selwyn, Canterbury, New Zealand.

This project uses observations identified during 10-minute Merlin Sound ID sessions to explore bird species richness, detection frequency and potential relationships with environmental conditions. It combines bird identification information, environmental data and interactive visualisations in a lightweight web dashboard.

**Project status:** Prototype in development.

## Features

- **Interactive filters:** Filter observations by time of day, background noise, wind conditions, species and survey date.
- **Survey summary statistics:** View the number of survey sessions, species recorded, mean species richness and latest session richness.
- **Data visualisations:** Explore species richness by date, start time and wind speed, alongside species detection frequency.
- **Species-by-session matrix:** Compare which birds were recorded during each survey.
- **Bird identification guide:** Browse bird photos, scientific names, taxonomic families, conservation context and descriptions.
- **Interactive species cards:** Select a bird to filter the dashboard and explore its observations.
- **Environmental context:** Compare bird observations with recorded weather and background noise conditions.
- **Incidental observations:** Keep records outside the formal 10-minute counts separate from survey results.

## Project objectives

The project aims to:

- Build a structured dataset from repeated backyard bird surveys.
- Explore patterns in bird detections and species richness over time.
- Investigate how recorded weather and background noise may relate to bird observations.
- Develop practical skills in GIS, data management and interactive data visualisation.
- Explore opportunities to automate environmental data preparation using FME.

## Data collection

Bird observations are collected during 10-minute listening sessions using Merlin Sound ID.

The dataset includes fields such as:

- Survey session ID and date
- Start and end times
- Bird species recorded
- Temperature and wind speed
- Weather conditions, cloud cover, rainfall and humidity
- Background noise and observation notes

The current dashboard is a prototype based on the first six survey sessions, covering 20 to 25 October 2026. The dataset and dashboard will be updated as more observations are collected.

Merlin Sound ID detections are treated as identification records rather than independently verified evidence of every bird's presence. Incidental observations are kept separate from the formal survey counts.

## Technology

- **HTML and CSS:** Dashboard structure, layout and styling.
- **JavaScript:** Filtering, calculations and interactive behaviour.
- **Chart.js:** Data visualisations.
- **Wikipedia:** Bird identification references and photographs retrieved through its API.
- **FME:** Planned workflow development for data preparation and environmental data integration.
- **GIS:** Environmental data exploration and spatial analysis opportunities.

## Running the dashboard

1. Download or clone this repository.
2. Open the HTML dashboard file in a modern web browser.
3. Use the filters to explore the survey sessions and species records.

An internet connection is required to load Chart.js from its CDN and retrieve bird photographs from Wikipedia.

No build process is required for the current standalone HTML prototype.

## Current limitations

- The dashboard currently contains only six survey sessions.
- The observations are entered directly into the JavaScript code rather than loaded from an automated data pipeline.
- Start time is currently used as a proxy for time relative to sunrise.
- Bird detections may be affected by identification accuracy, background noise, weather and survey conditions.
- The current sample is too small to support strong conclusions about bird behaviour or environmental relationships.
- Bird photographs depend on external services being available.

## Future development

Planned improvements include:

- Expanding the survey dataset through repeated observations.
- Integrating sunrise and sunset information from Open-Meteo.
- Developing an FME workflow to prepare and combine observation and weather data.
- Improving the bird identification panel with additional reference information and bird calls.
- Adding further temporal and environmental comparisons.
- Exploring GIS-based visualisation of bird observations and their environmental context.

## About

This is a personal learning project exploring backyard biodiversity, environmental data and GIS-related data visualisation in Canterbury, New Zealand.

The project is being developed incrementally as a practical portfolio example of data collection, data preparation, analysis and interactive dashboard design.
