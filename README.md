# New Brunswick Wildfire Map

A Leaflet + Esri-Leaflet web map showing active wildfires, fire perimeters, weather stations, radar, lightning density, smoke, AQHI, Sentinel-2 imagery, and aircraft over New Brunswick and surrounding areas.

Special thanks to the open data champions and maintainers.

Map Link: https://nbfiremap.github.io/NBFireMap/

---

## Features

- Esri Imagery basemap with custom panes and z-indexing for clean stacking.
- NB active wildfire points with status-aware markers and rich popups.
- Canadian active wildfire perimeters with auto-show labels at higher zoom.
- Environment Canada weather stations rendered as animated wind arrows with speed, temperature, and humidity readouts.
- NOAA base-reflectivity radar (time-enabled image service).
- MSC GeoMet lightning density (WMS).
- AQHI stations (feature layer) with category-coded badges.
- Optional Sentinel-2 imagery overlay.
- VIIRS thermal hotspot points.
- Optional smoke layer (Canadian forecast).
- Aircraft positions from OpenSky (rate-limited public API).
- “Fire Summary” drawer with live rollups (counts, new today/yesterday, total area) and quick-zoom to fires.

---

## Data Sources

### Wildfires

- **NB Active Fires (points)**  
  [Public_Fires/MapServer/0](https://gis-erd-der.gnb.ca/arcgis/rest/services/Fire_Dashboards/Public_Fires/MapServer/0) – Current NB wildfire points with fields including `FIRE_NAME`, `FIRE_STAT_DESC_E`, and `FIRE_SIZE`.

- **Active Wildfire Perimeters in Canada (polygons)**  
  [Active_Wildfire_Perimeters_in_Canada_View/FeatureServer/0](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/Active_Wildfire_Perimeters_in_Canada_View/FeatureServer/0) – Perimeters derived from hotspots identified in satellite imagery provided by the Canadian Wildland Fire Information System (CWFIS).

- **VIIRS Thermal Hotspots & Fire Activity (last 7 days)**  
  [Satellite_VIIRS_Thermal_Hotspots_and_Fire_Activity/FeatureServer/0](https://services9.arcgis.com/RHVPKKiFTONKtxq3/ArcGIS/rest/services/Satellite_VIIRS_Thermal_Hotspots_and_Fire_Activity/FeatureServer/0) – Detectable thermal activity from VIIRS satellites; product of NASA’s FIRMS program.

### Weather & Air Quality

- **Environment Canada Weather Stations**  
  [EnvironmentCanada/FeatureServer/0](https://services.arcgis.com/zmLUiqh7X11gGV2d/arcgis/rest/services/EnvironmentCanada/FeatureServer/0) – Hourly weather conditions for stations across Canada.

- **NOAA Radar – Base Reflectivity**  
  [radar_base_reflectivity_time/ImageServer](https://mapservices.weather.noaa.gov/eventdriven/rest/services/radar/radar_base_reflectivity_time/ImageServer) – MRMS composite radar with a four-hour moving time window.

- **MSC GeoMet – Lightning Density (WMS)**  
  [GeoMet WMS](https://geo.weather.gc.ca/geomet?service=WMS&request=GetCapabilities&version=1.3.0) (layer: `Lightning_2.5km_Density`) – Lightning density over most of Canada.

- **AQHI Stations**  
  [aqhi_stations_observations_realtime/FeatureServer/1](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/aqhi_stations_observations_realtime/FeatureServer/1) – Real-time AQHI station observations.

### Imagery & Smoke

- **Sentinel-2 Imagery**  
  [Sentinel2/ImageServer](https://sentinel.arcgis.com/arcgis/rest/services/Sentinel2/ImageServer) – Multispectral imagery from Sentinel-2 satellites; updated daily.

- **Wildfire Smoke (Canada, forecast)**  
  Example ArcGIS smoke forecast layer (provider-specific endpoint).

### Administrative & Reference

- **NB Provincial Boundary**  
  Provinces & Territories of Canada feature service (filtered to “New Brunswick”).

- **NB Crown Lands**  
  Crown land dataset managed by the Department of Natural Resources and Energy Development.

### Aviation

- **OpenSky Network – States API**  
  [API Docs](https://opensky-network.org/apidoc/rest.html#all-state-vectors) – Public ADS-B/Mode-S state vectors; rate-limited.

---

## How Layers Are Used

- **Rendering & Interactivity** – Feature layers are drawn with custom `DivIcon` markers and tooltips/popups. Image/WMS layers are stacked in dedicated panes for visual precedence.
- **Perimeter Labels** – Shown only at higher zoom levels to reduce clutter.
- **Summary Panel** – Aggregates NB Active Fires data to compute counts by status, “new today/yesterday,” and total burned area.
- **Aircraft** – OpenSky bounding box set to NB extent; icons rotate with heading, whitelist callsigns are highlighted.
