# NB Fire Map

An interactive web map for monitoring current and recent wildfire activity in New Brunswick, Canada.  
The map integrates multiple open data sources including wildfire perimeters, active fire points, smoke forecasts, and environmental conditions to provide situational awareness.

**Map:** [NBFireMap](https://www.nbfiremap.ca)

---

## Features

- **Active Fire Locations**: Displays active and extinguished fire points from Government of New Brunswick (GeoNB) data services.
- **Wildfire Perimeters**: Shows active wildfire boundaries across Canada.
- **Satellite Hotspots**: Includes MODIS and Sentinel-2 fire detections.
- **Smoke Forecasts**: NOAA surface smoke forecasts with a timeline animation.
- **Burn Restrictions**: Links to official NB burn restrictions and fire watch updates.
- **Environmental Layers**: Weather stations, lightning density, fire danger ratings, radar, and AQHI data.
- **Aircraft Tracking**: Integrates ADS-B flight positions from OpenSky Network (potentially identifying water bombers and support aircraft).
- **Community Context**: City and town markers with proximity tools to nearby fires.

---

## Data Sources and Ownership

This project relies on authoritative open data services. All data is the property of its respective owners:

- **Government of New Brunswick (GeoNB)**  
  - [Active Fire Data](https://www.gnb.ca/en/topic/laws-safety/emergency-preparedness-alerts/fire-watch.html)  
  - [NB Crown Land](https://geonb.snb.ca/)  
  Ownership: © Province of New Brunswick. Provided for public awareness.

- **Natural Resources Canada (CWFIS)**  
  - [Canadian Wildland Fire Information System (Fire Danger Rating)](https://cwfis.cfs.nrcan.gc.ca/home)  
  Ownership: © Government of Canada.

- **Environment and Climate Change Canada (ECCC)**  
  - [Weather and Lightning Layers](https://weather.gc.ca/)  
  - [Air Quality Health Index (AQHI)](https://www.canada.ca/en/environment-climate-change/services/air-quality-health-index.html)  
  Ownership: © Government of Canada.

- **NOAA National Weather Service**  
  - [NOAA Smoke Forecast (Surface Concentration)](https://www.weather.gov/)  
  Ownership: © United States Government, public domain.

- **NASA / Esri**  
  - [MODIS Fire Hotspots](https://earthdata.nasa.gov/)  
  - [Sentinel-2 Imagery via Esri Services](https://sentinel.esa.int/)  
  Ownership: © NASA / ESA. Licensed for research and public awareness.

- **OpenSky Network**  
  - [Aircraft Positions API](https://opensky-network.org/)  
  Ownership: © OpenSky Network contributors. Licensed for non-commercial use.

All data is used strictly for visualization and public information purposes. This repository does not modify, republish, or redistribute the original data.

---

## Acknowledgements

**Firefighters and emergency response teams** — for their ongoing work protecting lives, communities, and ecosystems.

**Open data champions** in New Brunswick, Canada, the United States, and internationally — for making critical environmental and geospatial data openly available.

**Developers and maintainers** of Leaflet, Esri Leaflet, and OpenSky Network libraries for enabling open geospatial analysis.

## Disclaimer

This is an unofficial tool created for situational awareness and data visualization.
For official wildfire information, alerts, and restrictions, consult:
[Government of New Brunswick Fire Watch](https://www.gnb.ca/en/topic/laws-safety/emergency-preparedness-alerts/fire-watch.html).
