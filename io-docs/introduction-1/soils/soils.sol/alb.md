---
description: Moist soil albedo of the top layer
---

# alb

**Code reference:** `soildb(isol)%ly(j)%alb` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L56)).

Ratio of solar radiation reflected by a moist soil surface at or near field capacity to the incident solar radiation (`fraction`, `0–1`; Fortran struct default: `0.1`). Under snow-free conditions, [`albedo.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/albedo.f90#L27-L30) uses only layer 1 (`soil%ly(1)%alb`) to compute daily surface albedo:

$$\alpha_{\text{day}} = \begin{cases} \alpha_{\text{soil}}, & \text{LAI} = 0 \\ 0.23(1 - e_a) + \alpha_{\text{soil}} \cdot e_a, & \text{LAI} > 0 \end{cases}$$

where $\alpha_{\text{soil}}$ is layer 1 `alb` and $e_a$ is the soil-cover weighting factor from residue and plant biomass. Deeper-layer `alb` values are parsed and reported in soil-property snapshots ([`soil_nutcarb_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L693)) only; [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L51) clamps the unused `sol%s%alb` field rather than `sol%ly(1)%alb`.
