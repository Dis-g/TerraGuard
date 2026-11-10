
# Historical Landslide Evidence

TerraGuard provides a Historical Occurrence Index (0–100) based on the distance-weighted density of recorded landslide events.

## API

```http
GET /api/v1/historical/assess?latitude=27.036&longitude=88.2627&radius_km=25
```

The live assessment endpoint also returns `historical_evidence`.

## Interpretation

- Nearby reported events contribute more to the index.
- Additional nearby records increase historical evidence.
- The default search radius is 25 km.
- Historical evidence is displayed separately from the ML score.

## Limitations

- The NASA static catalog export ends on 2016-03-07.
- The inventory is incomplete and affected by reporting bias.
- A zero index means no matching records were found, not that the location is safe.
- Historical occurrence is not a probability or calibrated susceptibility estimate.

Newer NASA COOLR or NRSC/ISRO inventory data can be incorporated when verified source files are available.
