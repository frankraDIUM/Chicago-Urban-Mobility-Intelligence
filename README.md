# 🚕 Chicago Urban Mobility Pattern Analysis Using Satellite Imagery,Taxi-Data and ML
This project analyzes urban mobility patterns in Chicago by combining satellite imagery (Sentinel-2), OpenStreetMap road data, population density, business licenses/POI data, and a large Chicago taxi dataset (~14 million trips in 2024–early 2026).


---
Dashboard Preview

<p align="center">
  <img src="https://github.com/frankraDIUM/Chicago-Urban-Mobility-Pattern-Analysis-Using-Satellite-Imagery-Taxi-Data-and-ML/blob/main/mobility_analysis_.gif" />
</p>

---




*1. Objectives*

- Detect and quantify vehicle density proxies from Sentinel-2 imagery
- Analyze spatiotemporal mobility trends using taxi data as ground truth
- Identify congestion hotspots and hidden demand areas
- Build predictive models for taxi trip volume (static + temporal)
- Evaluate the added value of satellite-derived features


*2. Data Sources*

- Satellite: Sentinel-2 Level-2A (10m resolution: B02, B03, B04, B08)
- Ground Truth: Chicago Taxi Trips 2024 (Parquet, ~14 million records)
- Road Network: Illinois OSM extract (illinois-260330.osm.pbf)
- Population: WorldPop 2020 (usa_ppp_2020_UNadj.tif)
- POI / Business: Chicago Business Licenses dataset
- Boundaries: Chicago Community Areas (77 areas)

## Key Results

- **Static Model** (community area level): R² = 0.666
- **Temporal Model** (hourly prediction): **R² = 0.954**, MAE = 294 trips
- **Strongest predictors**: Number of hotels, airport presence, distance to Loop
- **Satellite proxy (10m)**: Very limited predictive power once destination features are included

## Features

- Road mask & vehicle density proxy from Sentinel-2 (10m)
- Hotspot analysis (Getis-Ord Gi*)
- Residual analysis to find hidden demand
- Interactive Streamlit dashboard
- Temporal prediction tool (hour + day type)



## Tech Stack

- **Python** 3.11
- Geospatial: GeoPandas, Rasterio, Folium, Streamlit-Folium
- ML: XGBoost, Scikit-learn
- Data: PyArrow, Pandas

##  Main Findings

1. Taxi demand is strongly **destination-driven** (hotels, airports, restaurants, bars).
2. Sentinel-2 at 10m resolution provides limited additional value for mobility prediction.
3. O’Hare and Near North Side remain significant hidden hotspots.
4. South Side neighborhoods are systematically over-predicted.


