# Maharashtra Weather Analysis Dashboard

## Overview

This Power BI dashboard provides a comprehensive analysis of weather patterns across **Maharashtra, India**, covering rainfall and temperature data at both the **district** and **subdivision** level. It is designed to help users explore historical climate trends, identify extreme weather events, and compare monsoon versus non-monsoon performance across different regions and time periods.

The dashboard is structured across **7 interactive report pages**, each focusing on a specific aspect of Maharashtra's climate data.

---

## Dashboard Pages

### 1. 🏠 Key Metrics
The home/landing page providing a high-level summary of the most important weather statistics for Maharashtra.

**Key visuals include:**
- **Hottest Year** — the year with the highest recorded maximum temperature
- **Coolest Year** — the year with the lowest recorded minimum temperature
- **Rainiest Year** — the year with the highest total rainfall
- **Driest Year** — the year with the lowest total rainfall
- **KPI Cards** for Average Rainfall, Average Maximum Temperature (Tmax), Minimum Temperature (Tmin), and Monsoon Performance
- Navigation buttons to all other report pages

---

### 2. 🗺️ District-wise Rainfall
Explores rainfall distribution and trends broken down by **district**.

**Key visuals include:**
- **Shape Map** — Geographical map of Maharashtra showing rainfall distribution by district
- **Line Chart** — Total Rainfall Trend over years
- **Treemap** — Rainfall intensity breakdown (percentage share by intensity category)
- **KPI Cards** — Average Rainfall, Maximum Daily Rainfall, Difference from District Long Period Average (LPA)
- **Tables** — Rainiest and Driest districts
- **Slicers** — Filter by Year, Season, and custom date period

---

### 3. 🌡️ District-wise Temperatures
Focuses on temperature patterns (Tmax and Tmin) at the **district** level.

**Key visuals include:**
- **Shape Map** — Geographical map showing Tmax distribution by district
- **Line Charts** — Average Temperature Trends for both Tmax and Tmin over years
- **Multi-row Card** — Daily Tmax status breakdown
- **KPI Cards** — Average Tmax, Maximum Tmax, Tmin values, deviation from LPA, Heat Waves count
- **Tables** — Hottest and coolest districts
- **Slicers** — Filter by Year, Season, and custom date period

---

### 4. 🗺️ Subdivision-wise Rainfall
Similar to District-wise Rainfall but aggregated and analyzed at the **subdivision** level.

**Key visuals include:**
- **Shape Map** — Rainfall distribution across Maharashtra subdivisions
- **Line Chart** — Total Rainfall Trend over years
- **Treemap** — Rainfall intensity distribution
- **KPI Cards** — Average Rainfall, Maximum Rainfall Ever Recorded, Difference from Subdivision LPA
- **Tables** — Rainiest and Driest subdivisions, Subdivision-wise Rainfall Category
- **Slicers** — Filter by Year, Season, and custom date period

---

### 5. 🌡️ Subdivision-wise Temperatures
Mirrors the District-wise Temperatures page but at the **subdivision** level.

**Key visuals include:**
- **Shape Map** — Tmax distribution across subdivisions
- **Line Charts** — Average Temperature Trends for Tmax and Tmin
- **Multi-row Card** — Daily Tmax status
- **KPI Cards** — Tmax, Tmin, Heat Waves, deviation from LPA
- **Tables** — Hottest and coolest subdivisions
- **Slicers** — Filter by Year, Season, and custom date period

---

### 6. 🌧️ Monsoons Performance
Dedicated analysis of **monsoon season** rainfall performance across Maharashtra.

**Key visuals include:**
- **Donut Chart** — Yearly monsoon status distribution (e.g., Normal, Excess, Deficient)
- **Line Chart** — Average Rainfall Trend during monsoon years
- **KPI Cards** — Yearly Monsoon Status, Yearly Monsoon Index, Highest/Lowest Average Monsoon Year, Highest/Lowest Recorded Monsoons, Total yearly monsoon rainfall
- **Slicer** — Filter by year range

---

### 7. ☀️ Non-Monsoons Performance
Focuses on rainfall during **non-monsoon seasons** (Pre-Monsoon, Post-Monsoon, Winter).

**Key visuals include:**
- **Line Chart** — Average Rainfall Trend for non-monsoon periods
- **KPI Cards** — Total Non-Monsoon Rainfall, Total Pre-Monsoon Rainfall, Total Post-Monsoon Rainfall, Total Winter Rainfall
- **Tables** — Max and Min Non-Monsoon Year, Max Post-Monsoon Year, Max Pre-Monsoon Year
- **Treemap** — Rainfall intensity distribution
- **Card** — District with maximum non-monsoon rainfall
- **Slicers** — Filter by Year and custom date period

---

## Data Model

The dashboard is built on the following tables:

| Table | Description |
|-------|-------------|
| `records` | Core weather observation records — contains date, rainfall (`rain`), max temperature (`tmax`), min temperature (`tmin`), rain intensity, and deviation metrics |
| `dim_dist` | District dimension table — district names, LPA (Long Period Average) for monsoons |
| `dim_subd` | Subdivision dimension table — subdivision names and LPA for monsoons |
| `dim_season` | Season dimension — classifies records into seasons (Monsoon, Pre-Monsoon, Post-Monsoon, Winter) |
| `monsoons_performance` | Aggregated monsoon performance — yearly averages, totals, and statuses |
| `all_measures` | DAX measures table — calculated KPIs such as Average Rainfall, Heat Waves, Selected District/Subdivision, LPA differences, etc. |

---

## Filters & Interactivity

All pages (except the Key Metrics home page) support the following slicers:

- **Year** — Filter data by a specific year
- **Season** — Filter by season (Monsoon, Pre-Monsoon, Post-Monsoon, Winter)
- **Choose Period** — Custom date range picker for granular filtering

Visuals are cross-filtered, meaning clicking on a district in the map updates all other visuals on the page accordingly.

---

## Key Metrics Explained

| Metric | Description |
|--------|-------------|
| **LPA (Long Period Average)** | The historical average rainfall for a district/subdivision, used as a benchmark |
| **Difference from LPA** | How much current rainfall deviates from the historical average |
| **Tmax / Tmin** | Maximum and minimum daily temperature readings |
| **Heat Waves** | Count of days where temperatures exceeded heat wave thresholds |
| **Rain Intensity** | Categorical classification of daily rainfall (e.g., Light, Moderate, Heavy, Very Heavy) |
| **Monsoon Index** | An index score indicating the overall performance of the monsoon season |
| **Yearly Monsoon Status** | Classification of a monsoon year as Normal, Excess, Large Excess, Deficient, or Large Deficient |

---

## Geographic Coverage

The dashboard covers **Maharashtra, India**, using custom GeoJSON maps (`MH_DIST`) for accurate district and subdivision boundary rendering via Power BI Shape Maps.

Static reference images embedded in the dashboard include:
- Maharashtra Divisions map (English labels)
- Maharashtra Weather Analysis overview image

---

## Technical Details

| Property | Value |
|----------|-------|
| **File Format** | Power BI Desktop (.pbix) |
| **Power BI Theme** | AccessibleDefault |
| **File Size** | ~9.6 MB |
| **Number of Pages** | 7 |
| **Custom Visuals** | Shape Map (choropleth) |
| **Map Data** | Custom GeoJSON for Maharashtra districts and subdivisions |
| **License Badge** | CC BY-NC-SA (Creative Commons Non-Commercial Share-Alike) |

---

## How to Use

1. **Open** the `.pbix` file in **Power BI Desktop** (version supporting Shape Map visuals).
2. Start on the **Key Metrics** page for a summary overview.
3. Use the **navigation buttons** to move between pages.
4. Apply **slicers** (Year, Season, Period) on any page to filter data.
5. **Click on a district or subdivision** in the map to cross-filter all visuals on that page.
6. Use the **Rainiest/Driest/Hottest/Coolest** tables to quickly identify outlier regions or years.

---

*Dashboard created for the analysis of historical weather data across Maharashtra, India.*
