# 2025 Spanish Recap

A static year-in-review dashboard visualizing my 2025 Spanish language learning stats.

**Live site:** https://lpetersen4.github.io/2025-spanish-recap/

## What it shows

- Total hours of listening, reading, and speaking practice
- Monthly breakdown of all three skills
- Daily listening chart for every day of the year
- Cumulative listening progress over the year
- Highlights: best day, best month, longest streak

## Data

Manually tracked in `Spanish Tracking - 2025.csv` — one row per day, columns for Listening, Reading, and Speaking (minutes). Listening was tracked all year; Reading started in late July; Speaking started in mid-August.

## Tech

Plain HTML + JavaScript, no build step. Uses [Chart.js](https://www.chartjs.org/) for charts and [PapaParse](https://www.papaparse.com/) for CSV parsing, both via CDN. The CSV data is embedded inline so the page works when opened as a local file.
