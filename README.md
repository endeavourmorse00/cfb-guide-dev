# College Football TV Guide 🏈

A client-side web application and TV guide designed to prioritize college football viewing schedules based on personalized interest ratings. Hosted on GitHub Pages.

---

## 📌 Overview

This project eliminates manual spreadsheet calculation workflows by dynamically computing custom **Watch Scores** in the browser using static team and conference lookup values. The interface is optimized for both mobile and desktop screens, featuring a condensed card layout, multi-tier color coding, and real-time filtering controls.

---

## ✨ Features

* **Dynamic Watch Score Calculation:** Calculates matchup interest scores on the fly in JavaScript using the formula:

$$\text{Watch Score} = (\text{Away TeamValue} + \text{Away ConfValue}) + (\text{Home TeamValue} + \text{Home ConfValue})$$


* **Multi-Tier Color Badging:**
* **Elite (22+):** Dark Navy (`#003153`)
* **High (18–21):** Steel Blue (`#4682b4`)
* **Good (11–17):** Soft Blue (`#b0d0e6`)
* **Mid (5–10):** Ice Blue (`#f0f8ff`)
* **Low (0–4):** White / Light Slate


* **Comprehensive Real-Time Filters:**
* **Date Filter:** Auto-selects the nearest upcoming game slate (includes an "All Dates" view).
* **Minimum Watch Score:** Filter by interest thresholds (`0+`, `5+`, `11+`, `18+`, `22+`).
* **Team Search:** Real-time text search for any school.
* **Conference Filter:** Auto-populated dropdown matching games featuring selected conference members.
* **Network Filter:** Filter games by broadcast network (ABC, ESPN, FOX, CBS, SEC Network, etc.).
* **Time Slot Filter:** Group kickoffs into Early (Before 2:30 PM CT), Afternoon (2:30 PM–5:59 PM CT), or Night (6:00 PM+ CT).


* **Sorting Options:** Sort games chronologically by time, descending by score, or alphabetically by network.
* **Lightweight & Fast:** Pure vanilla JavaScript, CSS Grid, and HTML with zero runtime dependencies.
* **Privacy-Friendly Analytics:** Integrated with [GoatCounter](https://www.goatcounter.com/) for visitor tracking.

---

## 📁 Repository Structure

```text
├── index.html     # Main web interface, styling, filtering, and scoring logic
├── games.json     # Weekly schedule data (date, matchup, time, network)
├── teams.json     # Lookup table for team ratings, conference values, and affiliations
└── README.md      # Project documentation

```

---

## 🛠️ Data File Formats

### 1. `games.json`

Contains raw game schedule information. No score calculation required:

```json
[
  {
    "date": "2026-09-05",
    "matchup": "Clemson at LSU",
    "time": "6:30 pm",
    "network": "ABC"
  },
  {
    "date": "2026-09-12",
    "matchup": "Ohio State at Texas",
    "time": "6:30 pm",
    "network": "ABC"
  }
]

```

### 2. `teams.json`

Maps individual schools to their assigned base interest values and conference scores:

```json
{
  "LSU": {
    "teamValue": 20,
    "confValue": 3,
    "conference": "SEC"
  },
  "Clemson": {
    "teamValue": 7,
    "confValue": 2,
    "conference": "ACC"
  }
}

```

---

## 🚀 Deployment & Updates

1. **Deploying Changes:**
* Push or upload updated `index.html`, `games.json`, or `teams.json` files directly to the `main` branch.
* GitHub Pages will automatically build and publish updates in 1–2 minutes.


2. **Weekly Schedule Ingestion:**
* Update `games.json` with the new week's dates, matchups, kickoff times, and networks.
* Scores and filters update automatically on page load.