# 🎧 Spotify Music Analytics Dashboard

### Turn listening history into meaningful music insights.

An interactive **Power BI dashboard** designed to explore Spotify listening activity, discover music preferences, and analyze playback patterns through data visualization.

<p align="center">
  <strong>Power BI · DAX · Data Analytics · Data Visualization</strong>
</p>

---

## 📊 Project Overview

This project transforms music playback data into an interactive analytics dashboard. It helps users understand their listening habits, identify favorite genres and artists, and explore their most-played tracks and albums.

The dashboard combines KPI cards, charts, and ranked tables in a dark, Spotify-inspired interface.

## ✨ Key Features

- **Listening KPIs** — Track total listening minutes, songs, and artists.
- **Listening Activity** — Explore playback activity throughout the day.
- **Listening by Hour** — Identify changes in listening volume across hours.
- **Genre Analysis** — Visualize the distribution of listening across music genres.
- **Top Artists** — Compare artists using listening minutes and play counts.
- **Top Tracks** — Identify frequently played songs.
- **Top Albums** — Explore albums ranked by playback activity.
- **Quick Insights** — Present key findings in a compact summary panel.

## 🖥️ Dashboard Preview



![Spotify Music Analytics Dashboard](screenshots/dashboard-overview.png)

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Power BI | Dashboard development and visualization |
| DAX | Measures and analytical calculations |
| Power Query | Data preparation and transformation |
| Excel | Source data |
| GitHub | Project documentation and version control |

## 🧮 DAX Measures



### 1. Total Listening Minutes

```dax
Total Minutes =
SUM(Playback[MinutesPlayed])
```

### 2. Total Plays

```dax
Total Plays =
SUM(Playback[PlayCount])
```

### 3. Unique Tracks Played

```dax
Unique Tracks =
DISTINCTCOUNT(Playback[TrackID])
```

### 4. Track Plays

This measure maps track IDs from the Tracks table to the Playback table when the model requires explicit filter propagation.

```dax
Track Plays =
CALCULATE(
    SUM(Playback[PlayCount]),
    TREATAS(
        VALUES(Tracks[TrackID]),
        Playback[TrackID]
    )
)
```


## 📁 Repository Structure

```text
spotify-music-analytics-dashboard/
├── README.md
├── dashboard/
│   └── Spotify_Music_Analytics_Dashboard.pbix
├── screenshots/
│   └── dashboard-overview.png
├── data/
│   └── README.md
└── dax/
    └── measures.dax
```

## 🚀 Getting Started

1. Download or clone this repository.
2. Open the `.pbix` file using Microsoft Power BI Desktop.
3. If prompted, update the source-data path.
4. Refresh the data if the source file is available.
5. Explore the dashboard visuals and DAX measures.

## 💡 Skills Demonstrated

- Data modeling and aggregation
- DAX measure development
- Interactive dashboard design
- Analytical storytelling
- Data visualization and KPI reporting
- Project documentation

## 🔮 Potential Improvements

- Add date-range and genre slicers.
- Compare listening patterns across months.
- Build a dedicated recently played view.
- Improve tooltip details and drill-through navigation.
- Automate data refresh where supported.

## 👤 Author

**Your Name**

Aspiring Data Analyst | Power BI | SQL | Excel

Connect with me on [LinkedIn](https://www.linkedin.com/in/your-username/)
Explore my projects on [GitHub](https://github.com/your-username).

---

*This project is intended for educational and portfolio purposes. Spotify branding and music-related names belong to their respective owners.*
