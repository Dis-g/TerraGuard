
# TerraGuard
### India Landslide Research & Monitoring System

TerraGuard is a research prototype for location-based landslide screening in India. It combines historical reported landslide events, weather and soil-moisture data, and a machine-learning model to generate an indicative screening score through an interactive map dashboard.

<img width="1517" height="717" alt="Screenshot 2026-11-17 210922" src="https://github.com/user-attachments/assets/abc24cf1-632b-4157-8c25-2ade64be8fc8" />
<img width="1182" height="680" alt="Screenshot 2026-11-17 210307" src="https://github.com/user-attachments/assets/22444a71-c525-4c12-ad78-e8b166307f5d" />

## Features

- **Location-based assessment:** Submit coordinates to request a live assessment.
- **Interactive map dashboard:** Explore locations and view assessment results.
- **Weather-based inputs:** Uses recent weather information from Open-Meteo.
- **Historical event evidence:** Shows nearby reported landslide occurrences separately from the ML score.
- **ML-based screening:** Uses a Scikit-learn Random Forest model trained on historical event and spatially displaced background samples.
- **REST API:** FastAPI endpoints for health checks, event records, weather data, model metrics, and assessments.

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React, Vite, Leaflet |
| Backend | Python, FastAPI |
| Machine Learning | Scikit-learn, Pandas, NumPy, Joblib |
| Data | NASA Global Landslide Catalog, Open-Meteo |
| Deployment | Docker, Docker Compose |

## Project Structure

```text
TerraGuard/
├── backend/
│   ├── app/
│   │   ├── ml/             # Data pipeline, training and model artifacts
│   │   └── services/       # Weather, historical evidence and scoring
│   ├── data/               # Processed event inventory
│   └── requirements.txt
├── frontend/
│   └── src/                # React dashboard and map components
├── data/                   # Project data and demo observations
├── docs/                   # Data, methodology and deployment notes
└── docker-compose.yml
```

## Live Deployment

The frontend and backend are deployed on Vercel.

- **Frontend:** https://terra-guard-roan.vercel.app/
- **Backend API:** https://terra-guard-back.vercel.app/

## Model and Data Notes

- Historical event records are sourced from the **NASA Global Landslide Catalog**. The static export used by the project is current through **7 March 2016**.
- Historical weather features use **Open-Meteo ERA5 reanalysis**; live assessments request recent weather inputs from the Open-Meteo API.
- The training workflow pairs reported events with spatially displaced background samples. These background samples are not verified landslide-free observations.
- The model output is a relative event-discrimination score. Historical occurrence evidence is a separate index and is not a probability.
- Data coverage is incomplete and uneven. A location with no records in the loaded inventory should not be interpreted as having no landslide hazard.

For further details, see:
- [Data Sources](docs/DATA_SOURCES.md)
- [Data Methodology](docs/DATA_METHODOLOGY.md)
- [Historical Evidence](docs/HISTORICAL_EVIDENCE.md)
- [Deployment Guide](docs/DEPLOYMENT.md)
- [Validation Plan](docs/VALIDATION_PLAN.md)

## Disclaimer

TerraGuard is an academic/research prototype intended for exploration and further validation. It has not been established as an operational hazard-warning service. Model performance, data quality, spatial and temporal generalization, and score calibration require further validation by domain experts. Always follow official local-authority guidance during hazardous conditions.
