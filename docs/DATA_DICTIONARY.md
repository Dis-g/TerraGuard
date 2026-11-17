
# TerraGuard Data Dictionary

## Observation
One record represents a location, observation date and associated weather conditions.

## Model Features

| Field | Unit | Description |
|---|---|---|
| rain_24h_mm | mm | Rainfall over previous 24 hours |
| rain_72h_mm | mm | Rainfall over previous 72 hours |
| rain_7d_mm | mm | Rainfall over previous 7 days |
| soil_moisture_0_7cm_pct | % | Surface soil moisture |
| soil_moisture_7_28cm_pct | % | Subsurface soil moisture |
| elevation_m | metres | Elevation from weather data |

## Target
- `landslide_reported = 1`: Reported NASA landslide event.
- `landslide_reported = 0`: Spatially displaced pseudo-absence sample.

## Provenance
Records include event date, coordinates, source, sample type and matched event ID.
