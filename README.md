<div align="center">

# 🎬 Netflix Titles Analytics Dashboard

### 📺 Exploring the Netflix Catalog, built in Tableau

![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Data](https://img.shields.io/badge/Dataset-6%2C234%20Titles-141413?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-be185d?style=for-the-badge)

</div>

---

## 📌 About This Project

A single-page Tableau dashboard that turns the Netflix titles catalog into an explorable view of the platform's content: **where it comes from, how it's rated, what genres dominate, and how the Movie vs. TV Show mix has shifted over time** — plus a live search panel that pulls up the full detail card for any one title.

| 🧩 | What it covers |
|---|---|
| 🌍 | Where the catalog's content comes from, country by country |
| 🔞 | The rating mix (TV-MA, TV-14, TV-PG, R, …) across the whole catalog |
| 🎭 | The top 10 genres by title count |
| 📈 | How Movies vs. TV Shows have grown, year by year |
| 🔎 | A one-title lookup panel — rating, duration, genre, and synopsis |

---

## 🖥️ The Dashboard

**Filters:** `Type` (multi-select — Movie / TV Show) and `Title` (single-select search) apply across the whole page.

**Title detail panel:** pick any title from the `Title` filter and six linked cards update instantly — **Rating**, **Duration**, **Date Added**, **Release Year**, **Genre**, and **Description**.

**Visualizations:**
- 🗺️ **Total Movies & TV Shows by Country** — a filled map, countries colored/sized by title count (using Tableau's built-in geocoding on `Country`)
- ⭐ **Ratings** — bar chart of title count by content rating, sorted descending (TV-MA leads with 2,027)
- 🟠 **Movies & TV Shows Distribution** — packed bubbles showing the Movie/TV Show split (68.42% / 31.58% of 6,234 titles)
- 🎭 **Top 10 Genre** — horizontal bar of the ten most common `Listed In` genres (Documentaries leads with 299)
- 📈 **Total Movies & TV Shows by Years** — a stacked area chart of title count by `Date Added` year, split by Type

<img width="1535" height="834" alt="Tableau Dashboard" src="https://github.com/user-attachments/assets/407a6ab0-90d4-46b4-a2a2-b34cb286191d" />

---

## 🗃️ Data Source

A single flat table — **`netflix_titles.csv`** (6,234 titles, one row per Movie/TV Show) — connected directly into Tableau with no calculated fields; every visual is built from native columns and Tableau's built-in aggregations (`COUNT`, `% of Total`, auto date hierarchies, and built-in geocoding).

| Column | Description |
|---|---|
| `show_id` | Unique title identifier |
| `type` | Movie or TV Show |
| `title` | Title name |
| `director`, `cast` | Credits |
| `country` | Country/countries of production (geocoded for the map) |
| `date_added` | Date the title was added to Netflix |
| `release_year` | Original release year |
| `rating` | Content rating (TV-MA, TV-14, PG-13, …) |
| `duration` | Runtime in minutes, or number of seasons |
| `listed_in` | Genre(s) |
| `description` | Synopsis |

---

## 🧮 Fields & Tableau Techniques Used

| Worksheet | Field(s) | Technique |
|---|---|---|
| Total Movies & TV Shows by Country | `Country` → generated `Geometry`/`Latitude`/`Longitude` | Filled map, `COUNT(Show Id)` by color/size |
| Ratings | `Rating`, `Show Id` | Bar chart, `COUNT(Show Id)`, sorted descending |
| Movies & TV Shows Distribution | `Type`, `Show Id` | Packed bubbles, `COUNT(Show Id)` + **% of Total** quick table calculation |
| Top 10 Genre | `Listed In`, `Show Id` | Horizontal bar, `COUNT(Show Id)`, **Top 10** filter |
| Total Movies & TV Shows by Years | `Date Added` (year), `Type`, `Show Id` | Stacked/area chart over the auto **YEAR(Date Added)** date hierarchy |
| Rating / Duration / Date Added / Release Year / Genre / Descrption | `Title` filter-driven | Single-value text tables acting as a detail lookup card |

> 💡 No calculated fields are used anywhere in this workbook — every number on the dashboard comes from a native column plus a built-in Tableau aggregation or table calculation, which keeps the whole model easy to audit directly from the `Title` shelf.

---

## 🛠️ Tech Stack

![Tableau Desktop](https://img.shields.io/badge/-Tableau%20Desktop-E97627?style=flat-square&logo=tableau&logoColor=white)
![CSV](https://img.shields.io/badge/-CSV%20Data%20Source-217346?style=flat-square)

---

## 📁 Repository Structure

```
📦 netflix-titles-tableau-dashboard
 ┣ 🎬 netflix_titles.csv          → Raw source data (6,234 titles)
 ┣ 📊 Netflix_Dashboard.twb       → Tableau workbook (1 dashboard, 11 worksheets)
 ┣ 🖼️ assets/                     → Screenshot used in this README
 ┗ 📘 README.md
```

## 🚀 How to Explore

1. Open **`Netflix_Dashboard.twb`** in Tableau Desktop (or Tableau Public/Reader).
2. Keep `netflix_titles.csv` in the same folder so the data source reconnects automatically.
3. Use the **Type** and **Title** filters top-left to slice the dashboard or look up a specific title's details.

---

## 📜 License

MIT — feel free to fork, star, and use in your own portfolio.

## 👨‍💻 About Me

Hi, I'm **Mohamed Sobhy** — a graduate student and ML/Data Science researcher, working on data analytics and machine learning projects across research and applied domains.

🔗 GitHub: [M-M-Sobhy](https://github.com/M-M-Sobhy)
💼 LinkedIn: [Mohamed Mahmoud Sobhy](https://www.linkedin.com/in/mohamed-mahmoud-sobhy-668ba937a)
🎥 YouTube: [@M_Sob7y](https://www.youtube.com/@M_Sob7y)

---

<div align="center">💡 If this helped you, consider giving the repo a ⭐</div>
