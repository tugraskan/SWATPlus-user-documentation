---
description: >-
  Plant uptake factor for pesticide
---

# pl\_uptake

**Code reference:** `pestdb(ip)%pl_uptake` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L20)).

Plant uptake factor (a transpiration-stream concentration factor) used for root uptake by growing plants. By default the mass taken from a soil layer is ([`pest_pl_up.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_pl_up.f90#L94-L97)):

$$U = f\,\frac{W}{S + W + K}\,M$$

where:
- $U$ is pesticide uptake from the layer (`kg/ha`),
- $f$ is `pl_uptake` (dimensionless),
- $W$ is water taken up from the layer (`mm`),
- $S$ is effective soil water (`mm`; see [resistance\_n](resistance_n.md)),
- $K$ is sorption capacity (`mm`; from [soil\_ads](soil_ads.md)), and
- $M$ is pesticide mass in the layer (`kg/ha`).
