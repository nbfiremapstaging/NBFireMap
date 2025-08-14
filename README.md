# New Brunswick Wildfire Map

A Leaflet + Esri-Leaflet web map showing active wildfires, fire perimeters, weather stations, radar, lightning density, smoke, AQHI, Sentinel-2 imagery, and aircraft over New Brunswick and surrounding areas.

🌐 **Map Link:** [NBFireMap](https://nbfiremap.github.io/NBFireMap/)

---

## Features

- Esri Imagery basemap with custom panes and z-indexing for clean stacking.
- **NB Active Fires** split by status (Out of Control, Contained, Under Control, Being Patrolled) with rich popups.
- **Canadian wildfire perimeters** with auto-labels visible at higher zoom.
- **Fire Summary drawer**: counts, new today/yesterday, and total burned area with quick zoom to fires.
- **Environment Canada weather stations**: animated wind arrows with speed, temperature, and humidity.
- **NOAA radar** (time-enabled base reflectivity image service).
- **MSC GeoMet lightning density** (WMS).
- **AQHI stations** with category-coded badges.
- **Sentinel-2 imagery overlay** (optional).
- **VIIRS & MODIS hotspots** (last 48h / 7d).
- **Smoke forecast layer** (Canada).
- **Aircraft positions** from the OpenSky Network API.
- **NB boundary, crown lands, burn bans** overlays.
- Major NB city labels.
- Mobile-friendly UI with layer toggle and location control.

---

## Data Sources

### Wildfires
- **NB Active Fires (points)**  
  [Public_Fires/MapServer/0](https://gis-erd-der.gnb.ca/arcgis/rest/services/Fire_Dashboards/Public_Fires/MapServer/0)

- **Active Wildfire Perimeters in Canada (polygons)**  
  [Active_Wildfire_Perimeters_in_Canada_View/FeatureServer/0](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/Active_Wildfire_Perimeters_in_Canada_View/FeatureServer/0)

- **VIIRS Hotspots (7 days)**  
  [VIIRS/FeatureServer/0](https://services9.arcgis.com/RHVPKKiFTONKtxq3/ArcGIS/rest/services/Satellite_VIIRS_Thermal_Hotspots_and_Fire_Activity/FeatureServer/0)

- **MODIS Hotspots**  
  [MODIS/FeatureServer](https://services9.arcgis.com/RHVPKKiFTONKtxq3/arcgis/rest/services/MODIS_Thermal_v1/FeatureServer)

### Weather & Air Quality
- **Environment Canada Stations**  
  [EnvironmentCanada/FeatureServer/0](https://services.arcgis.com/zmLUiqh7X11gGV2d/arcgis/rest/services/EnvironmentCanada/FeatureServer/0)

- **NOAA Radar – Base Reflectivity**  
  [radar_base_reflectivity_time/ImageServer](https://mapservices.weather.noaa.gov/eventdriven/rest/services/radar/radar_base_reflectivity_time/ImageServer)

- **Lightning Density (WMS)**  
  [GeoMet WMS](https://geo.weather.gc.ca/geomet?service=WMS&request=GetCapabilities&version=1.3.0) (layer: `Lightning_2.5km_Density`)

- **AQHI Stations**  
  [aqhi_stations_observations_realtime/FeatureServer/1](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/aqhi_stations_observations_realtime/FeatureServer/1)

### Imagery & Smoke
- **Sentinel-2 Imagery**  
  [Sentinel2/ImageServer](https://sentinel.arcgis.com/arcgis/rest/services/Sentinel2/ImageServer)

- **Smoke Forecast (Canada)**  
  Example ArcGIS smoke forecast service.

### Administrative & Reference
- **NB Boundary**  
  Provinces & Territories of Canada (filtered to NB)

- **NB Crown Lands**  
  [Crown Lands FeatureServer](https://gis-erd-der.gnb.ca/server/rest/services/OpenData/Crown_Lands/FeatureServer/0)

- **NB Burn Bans**  
  [BurnCategories/MapServer](https://gis-erd-der.gnb.ca/gisserver/rest/services/FireWeather/BurnCategories/MapServer)

### Aviation
- **OpenSky Network – States API**  
  [API Docs](https://opensky-network.org/apidoc/rest.html#all-state-vectors)

---

## How the Map Works

- **Layers & Popups:** Each layer has custom rendering, tooltips, and popups tailored for clarity.
- **Perimeter Labels:** Shown only at zoom ≥ 11 to reduce clutter.
- **Fire Summary Panel:** Aggregates NB active fire data with Atlantic Time “new today/yesterday” tracking.
- **Aircraft:** Live aircraft positions over NB, heading-aware, with highlighted callsigns.
- **Mobile UX:** Toggle UI controls for a clean view.

---

## Errors & Omissions

This project relies on multiple live open-data services. Data availability, timeliness, and accuracy may vary. Some layers may be temporarily unavailable or load slowly. This map should not be considered authoritative for safety decisions—always refer to official government channels for emergency information.  

---

## Acknowledgements

- **Government of New Brunswick** – for providing open wildfire, crown land, and burn ban data services.  
- **Environment and Climate Change Canada** – for weather, radar, and AQHI data.  
- **Natural Resources Canada / CWFIS** – for fire danger ratings and perimeter data.  
- **NASA FIRMS / NOAA / OpenSky Network** – for global hotspot, satellite, and aviation data.  

🙏 Special thanks to the **open data champions and maintainers** whose work makes this project possible.  

---
