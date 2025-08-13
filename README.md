# 🗺️ New Brunswick Wildfire Map

An interactive Leaflet + Esri web map that displays **live wildfire status, perimeters, weather stations, air quality (AQHI), burn bans, smoke plumes**, and more — all focused on the province of **New Brunswick, Canada**.

---

## ✨ Features

- 🔥 **NB Active Wild Fires** with color-coded status icons  
- 🗺 **Active wildfire perimeters** with on-map area labels (zoom-based visibility)  
- 🌡 **Weather stations** showing wind direction/speed, temperature, and humidity  
- 🌬 **AQHI (Air Quality Health Index)** stations with risk categories  
- 🛰 **VIIRS satellite hotspots** from NASA FIRMS  
- ☁ **Smoke plume imagery** overlays  
- 🌲 **Crown lands boundaries** (visible at higher zoom)  
- 🚫 **Burn ban status** layer from GNB  
- ✈ **Aircraft tracking** from OpenSky Network (highlighting whitelisted callsigns)  
- 🔥 **Fire risk map** from CWFIS  
- 🖼 **Sentinel-2C imagery** overlay  
- 🏙 **City labels** for major NB communities  
- 📱 **Responsive design** with simplified mobile UI  

---

## 🔧 Technology Stack

- [Leaflet](https://leafletjs.com/) — interactive map engine  
- [Esri Leaflet](https://esri.github.io/esri-leaflet/) & [Esri Leaflet Image](https://esri.github.io/esri-leaflet/api-reference/esri-leaflet-image.html) — ArcGIS REST integration  
- [Font Awesome](https://fontawesome.com/) — map and legend icons  
- [OpenSky Network API](https://opensky-network.org/) — real-time aircraft positions  
- CSS custom properties — color theming & layout control  

---

## 📡 Data Sources

| Layer / Feature                | Source |
|--------------------------------|--------|
| **NB Active Wild Fires**       | [GNB Public Fires](https://gis-erd-der.gnb.ca/arcgis/rest/services/Fire_Dashboards/Public_Fires/MapServer/0) |
| **Weather Stations**           | [Environment Canada NB Stations](https://services.arcgis.com/zmLUiqh7X11gGV2d/ArcGIS/rest/services/EnvironmentCanada/FeatureServer/0) |
| **AQHI**                       | [AQHI Realtime Observations](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/aqhi_stations_observations_realtime/FeatureServer/1) |
| **Fire Perimeters**            | [Active Wildfire Perimeters (Canada)](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/Active_Wildfire_Perimeters_in_Canada_View/FeatureServer/0) |
| **Crown Lands**                 | [GNB Open Data Crown Lands](https://gis-erd-der.gnb.ca/server/rest/services/OpenData/Crown_Lands/FeatureServer/0) |
| **Burn Bans**                   | [GNB Burn Categories](https://gis-erd-der.gnb.ca/gisserver/rest/services/FireWeather/BurnCategories/MapServer) |
| **VIIRS Hotspots**              | [NASA FIRMS VIIRS](https://firms.modaps.eosdis.nasa.gov/) via ArcGIS |
| **Smoke Imagery**               | [ESRI Hosted ImageServer](https://enterpriseim.esriservices.ca/server/rest/services/Hosted/Aug12/ImageServer) |
| **Fire Risk Map**               | [CWFIS WMS](https://cwfis.cfs.nrcan.gc.ca/geoserver/public/wms) |
| **Sentinel-2C Imagery**         | [Sentinel-2 ArcGIS ImageServer](https://sentinel.arcgis.com/arcgis/rest/services/Sentinel2/ImageServer) |
| **Aircraft**                    | [OpenSky Network](https://opensky-network.org/api/states/all) |
| **NB Boundary**                 | [Provinces & Territories of Canada](https://services.arcgis.com/wjcPoefzjpzCgffS/ArcGIS/rest/services/Provinces_and_Territories_of_Canada/FeatureServer/0) |
| **City Locations**              | Static coordinates (local data) |

Special thanks to the champions of open and free data in New Brunsick!
