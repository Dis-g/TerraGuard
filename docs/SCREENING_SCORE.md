
# Composite Landslide Screening Score

TerraGuard calculates a heuristic screening index between 0 and 100.

## Component Weights

| Component | Weight |
|---|---:|
| Historical event count within 25 km | 30% |
| Nearest reported event proximity | 20% |
| Historical event recency | 10% |
| ML relative event score | 20% |
| Recent rainfall | 15% |
| Soil moisture | 5% |

Missing components are excluded and remaining weights are renormalized.

## Interpretation

The score combines historical inventory evidence, weather conditions and the ML model output.

It is NOT:
- A calibrated landslide probability.
- An official hazard classification.
- An operational forecast or evacuation instruction.

Rainfall and soil-moisture normalization use heuristic thresholds.

The model is trained using reported events and pseudo-absence samples. Terrain features such as slope, geology and land cover are not yet included.

TerraGuard is a research prototype, not an operational warning system.
