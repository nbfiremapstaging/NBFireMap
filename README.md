# New Brunswick Wildfire Map

A Leaflet + Esri‑Leaflet web map showing NB wildfire points, wildfire perimeters, weather stations, radar, lightning density, smoke, AQHI, and MODIS hotspots for New Brunswick and surrounding areas.

**Map:** [NBFireMap](https://nbfiremap.github.io/NBFireMap/)

---

## Features

- Esri Imagery basemap with custom panes and z‑indexing for clean stacking.
- **NB wildfire points** loaded from local GeoJSON (`active_fires.json`, `out_fires.json`) with rich popups and clustering.
- **Fire Status filter** (Out of Control, Contained, Under Control, Being Patrolled, Being Monitored, Extinguished). *Extinguished* is off by default. If all statuses are off, no fire points are shown.
- **Canadian wildfire perimeters** with auto‑labels that appear at higher zoom.
- **Fire Summary drawer** (Atlantic time): counts, new today/yesterday, extinguished today/yesterday, total burned area, and quick zoom to fires. Drawer content scrolls on mobile.
- **Environment and Climate Change Canada weather stations** with heading‑aware wind icons and tooltips; cluster icons display the nearest station symbol plus a count badge.
- **NOAA radar** (time‑enabled base reflectivity image service).
- **MSC GeoMet lightning density** (WMS) with periodic refresh.
- **AQHI stations** with category‑coded badges.
- **MODIS hotspots** (last 48 hours and last 7 days).
- **Fire Danger (CWFIS)** overlay.
- **Smoke forecast layer** (Canada).
- Mobile‑friendly UI with **Show/Hide Layers**, **Reset Map View**, and **Fire Summary** buttons.

> Note: Provincial boundary, burn bans, crown lands, Sentinel‑2 imagery, VIIRS hotspots, and aircraft tracking are not included in this build.

---

## Data Sources

### Wildfires
- **NB Wildfire Points (local cache used by the map)**  
  `active_fires.json`, `out_fires.json` (derived periodically from  
  [Public_Fires/MapServer/0](https://gis-erd-der.gnb.ca/arcgis/rest/services/Fire_Dashboards/Public_Fires/MapServer/0))

- **Active Wildfire Perimeters in Canada (polygons)**  
  [Active_Wildfire_Perimeters_in_Canada_View/FeatureServer/0](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/Active_Wildfire_Perimeters_in_Canada_View/FeatureServer/0)

- **MODIS Hotspots — Last 48 hours**  
  [MODIS_Thermal_v1/FeatureServer/0](https://services9.arcgis.com/RHVPKKiFTONKtxq3/arcgis/rest/services/MODIS_Thermal_v1/FeatureServer/0)

- **MODIS Hotspots — Last 7 days**  
  [MODIS_Thermal_v1/FeatureServer/1](https://services9.arcgis.com/RHVPKKiFTONKtxq3/arcgis/rest/services/MODIS_Thermal_v1/FeatureServer/1)

### Weather & Air Quality
- **Environment Canada Stations**  
  [EnvironmentCanada/FeatureServer/0](https://services.arcgis.com/zmLUiqh7X11gGV2d/arcgis/rest/services/EnvironmentCanada/FeatureServer/0)

- **NOAA Radar – Base Reflectivity (time‑enabled)**  
  [radar_base_reflectivity_time/ImageServer](https://mapservices.weather.noaa.gov/eventdriven/rest/services/radar/radar_base_reflectivity_time/ImageServer)

- **Lightning Density (WMS)**  
  [GeoMet WMS](https://geo.weather.gc.ca/geomet?service=WMS&request=GetCapabilities&version=1.3.0)  
  Layer: `Lightning_2.5km_Density`

- **AQHI Stations**  
  [aqhi_stations_observations_realtime/FeatureServer/1](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/aqhi_stations_observations_realtime/FeatureServer/1)

### Fire Danger & Smoke
- **Fire Danger (CWFIS)**  
  WMS: `public:fdr_current`  
  Endpoint: `https://cwfis.cfs.nrcan.gc.ca/geoserver/public/wms`

- **Wildfire Smoke (Canada, forecast)**  
  [Hosted/Aug12/ImageServer](https://enterpriseim.esriservices.ca/server/rest/services/Hosted/Aug12/ImageServer)

---

## How the Map Works

- **Layers & Popups:** Tailored rendering, tooltips, and popups for clarity.
- **Perimeter Labels:** Shown at zoom ≥ 11 to reduce clutter.
- **Fire Summary Panel:** Aggregates NB fire data from local GeoJSON with Atlantic‑time calculations for “today” and “yesterday.”
- **Weather Clusters:** Cluster icons show the nearest station’s wind symbol plus a count badge.
- **Controls:** “Show/Hide Layers” toggles the UI, “Reset Map View” restores the initial view, and “Fire Summary” opens the drawer.

---

## Errors & Omissions

This project relies on multiple live open‑data services. Data availability, timeliness, and accuracy may vary, and some services may be temporarily unavailable. Do not rely on this map for safety‑critical decisions; always consult official government channels for emergency information.

---

## Acknowledgements

Thank you to the open data teams and service maintainers whose work enables this map:

- **Government of New Brunswick** — wildfire data and other public services  
- **Environment and Climate Change Canada** — weather, radar, and AQHI data  
- **Natural Resources Canada / CWFIS** — fire danger ratings and perimeter data  
- **NASA/NOAA partners** — global satellite hotspot services
