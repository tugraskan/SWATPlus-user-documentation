---
description: "Available water capacity value for the soil"
---

# awc

**Code reference:** `soil_lte(k)%awc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L7)).

Available water capacity of the soil (`mm H2O/mm soil`; Fortran struct default: `0.`). During HRU-LTE initialization in [`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L258), SWAT+ scales it by the HRU-LTE soil profile depth $D_{\text{soil}}$ (mm):

$$\text{AWC}_{\text{mm}} = \text{awc} \cdot D_{\text{soil}}$$

where $\text{AWC}_{\text{mm}}$ is depth-integrated available water capacity (mm), $\text{awc}$ is `awc` (`mm H2O/mm soil`), and $D_{\text{soil}}$ is the HRU-LTE soil profile depth (mm).

The resulting depth-integrated storage $\text{AWC}_{\text{mm}}$ (mm) sets initial soil water ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L261)), percolation travel time ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L263)), evapotranspiration, and excess-water thresholds for lateral flow and percolation in [`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L180-L319).
