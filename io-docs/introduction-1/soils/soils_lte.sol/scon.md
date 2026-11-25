---
description: "Saturated hydraulic conductivity of the soil"
---

# scon

**Code reference:** `soil_lte(k)%scon` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L9)).

Saturated hydraulic conductivity of the soil (`mm/hr`; Fortran struct default: `0.`), copied to `hlt%sc` in [`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L260). It is used to compute percolation travel time ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L263)) and lateral subsurface flow ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L300)):

$$t_{\text{perc}} = \frac{\text{UL}_{\text{mm}} - \text{AWC}_{\text{mm}}}{K_{\text{sat}}}, \qquad Q_{\text{lat}} = 0.024 \cdot f_{\text{sw}} \cdot K_{\text{sat}} \cdot \frac{S}{L_{\text{slp}}}$$

where $K_{\text{sat}}$ is `scon` (mm/hr), $\text{UL}_{\text{mm}}$ and $\text{AWC}_{\text{mm}}$ are scaled porosity and available water capacity (mm), $f_{\text{sw}}$ is the excess-water saturation factor, $S$ is slope, and $L_{\text{slp}}$ is slope length (m).
