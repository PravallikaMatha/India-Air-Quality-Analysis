# 🌫️ India Air Quality Analysis (2017–2022)
### Exploratory Data Analysis of PM2.5 Pollution · NCAP Policy Evaluation · Population-Pollution Nexus

---

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?style=flat&logo=pandas)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter)
![Data](https://img.shields.io/badge/Records-1M+-green?style=flat)
![Stations](https://img.shields.io/badge/Monitoring%20Stations-561-orange?style=flat)

---

## 📌 Project Overview

This project performs a comprehensive analysis of India's air pollution landscape using **~1 million daily PM2.5 readings** from the Central Pollution Control Board (CPCB), spanning **561 monitoring stations** across **31 states** from 2017 to 2022.

The analysis addresses six interconnected research dimensions:

| Dimension | Focus |
|-----------|-------|
| **State-Level Patterns** | Which states carry the highest pollution burden? When do hazardous episodes cluster? |
| **Station-Level Deep Dive** | What happens at individual monitoring points — seasonal cycles, weekday effects? |
| **Temporal Trends** | Is India's air quality improving? How do monsoon and winter shape annual patterns? |
| **Population × Pollution** | Does population density predict PM2.5 exposure? |
| **Geographic Analysis** | Area-normalised pollution and monitoring station density |
| **Policy Evaluation** | Has the National Clean Air Programme (NCAP) reduced PM2.5 in funded cities? |

---

## 📊 Dataset Description

| File | Records | Description |
|------|---------|-------------|
| `Data.csv` | 1,048,575 rows | Daily PM2.5 & PM10 from CPCB stations (station, city, state, lat/lon, timestamp) |
| `NCAP_Funding.csv` | 131 cities | NCAP fund releases by city/state for FY2019–20, FY2020–21, FY2021–22 and utilisation % |
| `State_data.csv` | 31 states | Census-based population and geographic area per state |

**PM2.5 context:** The WHO safe guideline is **5 µg/m³ (annual)** / **15 µg/m³ (24-hr)**. India's NAAQS standard is **60 µg/m³**. Multiple states in this dataset average above 100 µg/m³.

---

## 🔍 Key Findings

- **Northern Indo-Gangetic Plain** states (Delhi, UP, Bihar, Rajasthan) consistently record PM2.5 levels 3–5× the Indian national standard
- **Delhi's November–January** period is chronically hazardous — driven by stubble burning, cold thermal inversions, and transboundary transport of pollutants
- **Monsoon provides 20–60% PM2.5 relief** across most states via wet deposition, but the respite is temporary
- **Delhi PM2.5 is 2–4× higher than Mumbai** year-round, reflecting structural differences in geography, transport, and source mix
- **COVID-19 lockdown** (2020) is visible as a clear dip in Delhi's monthly heatmap — one of the few natural experiments in urban air quality
- **NCAP-funded states** show higher PM2.5 on average — expected, since funds were directed at the most polluted cities, not as an indicator of policy failure
- **Population density explains <40% of PM2.5 variance** — industrial structure, topography, and wind patterns matter more
- **Monitoring coverage is severely unequal** — large states like Uttar Pradesh and Madhya Pradesh remain critically under-monitored relative to their populations

---

## 📁 Project Structure

```
india-air-quality-analysis/
│
├── India_Air_Quality_Analysis.ipynb   # Main analysis notebook (57 cells, fully documented)
│
├── Data.csv                           # CPCB PM2.5/PM10 station-level readings (2017–2022)
├── NCAP_Funding.csv                   # National Clean Air Programme funding data
├── State_data.csv                     # State population & area demographics
│
└── README.md                          # This file
```

---

## ⚙️ Setup & Usage

### Prerequisites

```bash
Python 3.9+
```

### Installation

```bash
git clone https://github.com/<your-username>/india-air-quality-analysis.git
cd india-air-quality-analysis
pip install pandas numpy matplotlib seaborn jupyter
```

### Run the Notebook

```bash
jupyter notebook India_Air_Quality_Analysis.ipynb
```

> **Note:** Place all three CSV files in the same directory as the notebook, or update the file paths in Section 2 (Setup & Data Loading).

---

## 🛠️ Technical Stack

| Tool | Purpose |
|------|---------|
| **Pandas** | Data loading, cleaning, groupby aggregations, time-series resampling |
| **NumPy** | Numerical operations, correlation, trend-line fitting |
| **Matplotlib** | Bar charts, line plots, scatter plots, annotated visualisations |
| **Seaborn** | Heatmaps, styled grid aesthetics |
| **Jupyter Notebook** | Interactive, reproducible analysis environment |

---

## 📈 Analyses Performed

### Part 1 — State-Level PM2.5 Patterns
- All-time average PM2.5 ranking across 31 states with NAAQS/WHO benchmark lines
- Identification of hazardous days (PM2.5 > 300 µg/m³) per state in 2023
- PM2.5 variability (standard deviation) by state — episodic vs. chronic pollution diagnosis
- Least-polluted state identification (2020–2021 average)

### Part 2 — Station-Level Deep Dive
- Peak pollution station in August 2020 (post-lockdown rebound)
- Seasonal PM2.5 decomposition at Kalaburagi KSPCB station (2018)
- Weekday vs. weekend PM2.5 patterns with monthly time series (2021)

### Part 3 — Temporal & Seasonal Trends
- Summer → Monsoon PM2.5 percentage change by state (2022) — the monsoon cleansing effect
- Delhi PM2.5 monthly heatmap (2017–2022) — reveals COVID dip and winter signatures
- Delhi vs. Mumbai long-run PM2.5 comparison with benchmark lines

### Part 4 — Population × Pollution Correlation
- Population-per-monitoring-station analysis — monitoring equity assessment
- Per-capita PM2.5 exposure ranking for 2023 — top 5 most burden-heavy states
- Population density vs. PM2.5 scatter with Pearson correlation
- Maharashtra vs. Madhya Pradesh case study — why density ≠ pollution

### Part 5 — Geographic & Spatial Analysis
- Area-normalised PM2.5 (µg/m³ per km²) — pollution intensity by state geography
- Monitoring station density (stations per 10,000 km²) — identifies monitoring deserts

### Part 6 — NCAP Policy Evaluation
- Funded vs. non-funded states PM2.5 comparison (2021)
- Assam PM2.5 time series with NCAP launch marker (2019)
- State area vs. total NCAP funding scatter — was allocation geographically equitable?

---

## 💡 Limitations & Future Work

**Limitations:**
- Data ends in early 2022; post-NCAP evaluation window is short for causal inference
- Missing values in PM2.5 (~15%) were dropped rather than imputed
- Analysis uses station-level averages, which may not represent city-wide exposure

**Future Extensions:**
- Satellite-derived PM2.5 (MODIS/Sentinel) for areas with no ground stations
- Difference-in-differences design to evaluate NCAP causal impact
- Machine learning forecasting of PM2.5 using meteorological covariates (wind, temperature, humidity)
- Interactive choropleth maps using Plotly/Folium for geographic visualisation
- Health burden estimation using WHO concentration–response functions

---

## 📚 Data Sources

- **Air Quality Data:** [Central Pollution Control Board (CPCB)](https://cpcb.nic.in/) — National Ambient Air Quality Monitoring
- **NCAP Funding:** Ministry of Environment, Forest and Climate Change (MoEFCC) — Parliamentary records
- **Demographics:** Census of India 2011 (population projections)

---

## 🤝 Contributing

Pull requests and issue reports are welcome. If you extend this analysis with satellite data, additional years, or ML models, please open a PR!

---

## 📄 License

This project is released under the [MIT License](LICENSE).

---

*Analysed by [Your Name] | B.Tech Mechanical Engineering | IIT Gandhinagar*
