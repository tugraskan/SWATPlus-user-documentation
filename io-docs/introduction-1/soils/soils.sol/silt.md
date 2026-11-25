---
description: Silt content of the soil layer
---

# silt

**Code reference:** `soildb(isol)%ly(j)%silt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L53)).

Percent by weight of soil particles that have an equivalent diameter between `0.05` and `0.002` mm (`%`; Fortran struct default: `60.0`). Surface-layer silt enters the detached silt fraction in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L110-L115) (and [`soil_text_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_text_init.f90#L39-L43)):

$$\text{det}_{\text{sil}} = 0.13 \cdot \frac{\text{silt}_1}{100}$$

where $\text{det}_{\text{sil}}$ is the detached silt fraction (dimensionless) and $\text{silt}_{1}$ is surface-layer `silt` (%).

It is also used in overland sediment transport ([`ero_ovrsed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ovrsed.f90#L90)), slow humus initialization ([`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_nutcarb_init.f90#L163-L170)), and surface sand recalculation ([`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L179)).
