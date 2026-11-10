
# Real Data Methodology

## 1. Landslide Inventory

NASA Global Landslide Catalog records provide the positive samples.

The India subset is generated using event dates and geographic coordinates.

## 2. Training Dataset

Two sample types are generated:

- Positive: Reported landslide event.
- Negative: Randomly displaced background point, 12–25 km from the event, matched to its date.

Negative samples are pseudo-absences, not verified non-landslide observations.

## 3. Weather Features

Open-Meteo ERA5 historical data provides:

- 24-hour rainfall accumulation.
- 72-hour rainfall accumulation.
- 7-day rainfall accumulation.
- Surface and subsurface soil moisture.
- Elevation.

Weather data covers the seven complete days before the event date. The event date is excluded.

## 4. Model Training

A Random Forest classifier is trained using six environmental features.

Missing values are handled using median imputation.

Matched event/control pairs are kept together using GroupShuffleSplit.

## 5. Limitations

- NASA catalog coverage is incomplete.
- Pseudo-absence labels may contain unreported landslides.
- ERA5 has relatively coarse spatial resolution.
- The validation split is not geographically or temporally independent.
- Slope, geology and land cover are not included.

The model produces a relative event-discrimination score, not a calibrated probability.
