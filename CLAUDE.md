# 2025 Spanish Recap - Project Guide

## Goal
Build a static webpage that visualizes 2025 Spanish language learning stats from a CSV file.

## Data

**File:** `Spanish Tracking - 2025.csv`

**Columns:** Year, Month, Day, Listening, Reading, Speaking, Writing

**Units:** Minutes per day

**Important CSV quirks:**
- Year and Month columns are sparse — only filled on the first row of each year/month; all other rows leave them blank
- Must forward-fill Year and Month when parsing
- Writing column is empty throughout (all blank)
- Reading data starts ~July 31; Speaking data starts ~August 19

**Date range:** Jan 1 – Dec 31, 2025 (366 rows, full year)

## Tech Stack
- Plain HTML + CSS + JavaScript (no build step, single file or small set of files)
- [Chart.js](https://www.chartjs.org/) for charts (CDN is fine)
- [PapaParse](https://www.papaparse.com/) for CSV parsing (CDN is fine)

Keep it simple — no React, no bundler, no npm.

## Key Stats to Display

**Summary cards (top of page):**
- Total minutes per skill: Listening, Reading, Speaking
- Total combined minutes
- Days tracked / days with activity

**Charts:**
- Daily listening minutes bar chart (full year, Jan–Dec)
- Monthly totals grouped bar chart (Listening vs Reading vs Speaking per month)
- Cumulative listening minutes line chart over the year

**Milestones / highlights:**
- Best single day (most listening minutes)
- Best month
- Current streak / longest streak

## Design Notes
- Light theme preferred (easier on eyes, looks like a "recap" dashboard)
- Color palette suggestion: teal/cyan for Listening, orange for Reading, purple for Speaking
- Inspired by year-in-review / Spotify Wrapped style
- Mobile-friendly layout

## CSV Parsing Notes

When parsing, forward-fill the Month column:
```js
let currentMonth = '';
rows.forEach(row => {
  if (row.Month) currentMonth = row.Month;
  row.Month = currentMonth;
});
```

Month names in CSV are full English names (January, February, ...).

Filter out rows where Day is blank or Listening is 0/blank before computing streaks.

## File Structure
```
index.html       # main page (can be a single self-contained file)
data.csv         # symlink or copy of "Spanish Tracking - 2025.csv"
```

Or embed the CSV data inline in the HTML to avoid CORS issues when opening locally.
