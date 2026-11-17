
# TerraGuard Data Sources

## 1. Landslide Inventory

**NASA Global Landslide Catalog**

Used for historical reported-event records.

Static export:
https://catalog.data.gov/dataset/global-landslide-catalog-export-75464

The available static export ends on 2016-03-07.

**NRSC/ISRO Landslide Atlas**

https://www.nrsc.gov.in/nrscnew/resources_atlas_landslide.php

Potential source for a more comprehensive Indian landslide inventory.

## 2. Historical Weather

**Open-Meteo Historical Weather API**

https://open-meteo.com/en/docs/historical-weather-api

ERA5 reanalysis provides:
- Hourly precipitation.
- Surface soil moisture.
- Subsurface soil moisture.
- Elevation metadata.

## 3. Live Weather

**Open-Meteo Forecast API**

https://open-meteo.com/en/docs

Used to retrieve recent weather conditions for location-based assessments.

## 4. Future Data Integration

- NRSC/ISRO geospatial landslide inventory.
- Copernicus Digital Elevation Model.
- Terrain slope and land-cover datasets.
- Geological and drainage information.

All external datasets must retain source, version, units, resolution and observation timestamps.
