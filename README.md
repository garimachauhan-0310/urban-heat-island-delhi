# 🌡️ Urban Heat Island Analysis — Delhi

A data analysis project that uses **Google Earth Engine**, **satellite imagery**, and **machine learning** to study urban heat patterns over Delhi (2015–2023) and predict future Land Surface Temperature trends.

---

## 📌 Overview

This project analyzes the **Urban Heat Island (UHI)** effect in Delhi using Landsat 8 satellite data. It computes vegetation and urbanization indices, builds ML models to predict surface temperature, performs temporal trend analysis, and identifies heat hotspots through clustering and interactive maps.

---

## 🛠️ Tech Stack

| Tool                      | Purpose                                              |
| ------------------------- | ---------------------------------------------------- |
| Google Earth Engine (GEE) | Satellite image retrieval & processing               |
| `geemap`                  | Interactive GEE map visualization                    |
| `pandas`                  | Data wrangling                                       |
| `scikit-learn`            | ML models (Linear Regression, Random Forest, DBSCAN) |
| `matplotlib` / `seaborn`  | Data visualization                                   |
| `folium`                  | Interactive geospatial heatmaps                      |

---

## 📊 Key Features

### Remote Sensing Indices

- **NDVI** — Normalized Difference Vegetation Index (measures greenery)
- **NDBI** — Normalized Difference Built-up Index (measures urbanization)
- **LST** — Land Surface Temperature (derived from Landsat Band 10)
- **UHI** — Urban Heat Island Index (normalized LST)

### Machine Learning

- **Linear Regression** and **Random Forest Regressor** trained to predict LST from NDVI and NDBI
- Feature importance analysis showing which index drives temperature more

### Temporal Analysis (2015–2023)

- Year-by-year average LST, NDVI, and NDBI over Delhi
- Correlation analysis between vegetation loss and rising temperatures
- **Future temperature prediction** for 2025–2027 using linear trend extrapolation

### Hotspot Detection

- **DBSCAN clustering** on spatial + temperature features to identify heat hotspot zones
- Interactive **Folium map** with circle markers and a heatmap layer

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- A [Google Earth Engine](https://earthengine.google.com/) account

### Installation

```bash
pip install earthengine-api geemap pandas scikit-learn matplotlib seaborn folium
```

### Authentication

```python
import ee
ee.Authenticate()
ee.Initialize(project='your-gee-project-id')
```

Replace `'da-project-492516'` in the notebook with your own GEE project ID.

### Run

Open `DA_Project.ipynb` in Jupyter or VS Code and run cells top to bottom.

---

## 📁 Project Structure

```
DA_Project.ipynb   # Main analysis notebook
README.md
```

---

## 📈 Results Summary

- Random Forest outperforms Linear Regression in predicting LST from spectral indices
- Clear negative correlation between NDVI (vegetation) and LST — more green = cooler
- LST trend shows a measurable rise over 2015–2023 in the Delhi ROI
- DBSCAN successfully identifies high-temperature clusters on the interactive map

---

## 📍 Region of Interest

**Delhi, India** — Bounding box: `[77.0°E, 28.4°N, 77.5°E, 28.9°N]`  
Data filtered for **April–June** (peak summer) with cloud cover < 10%.

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).
