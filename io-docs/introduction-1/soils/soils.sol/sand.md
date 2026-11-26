---
description: Sand content of the soil layer
---

# sand

**Code reference:** `soildb(isol)%ly(j)%sand` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L54)).

Percent by weight of soil particles that have an equivalent diameter between `2.0` and `0.05` mm (`%`; Fortran struct default: `30.0`). In [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L108-L114), surface-layer sand is first used to compute the detached sand fraction:

$$\text{det}_{\text{san}} = \frac{\text{sand}_1}{100} \left(1 - \frac{\text{clay}_1}{100}\right)^{2.49}$$

where $\text{det}_{\text{san}}$ is the detached sand fraction (dimensionless), $\text{sand}_{1}$ is surface-layer `sand` (%), and $\text{clay}_{1}$ is surface-layer [clay](clay.md) (%).

At the end of [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L179), layer 1 sand is unconditionally recomputed from clay and silt:

$$\text{sand}_1 = 100 - \text{clay}_1 - \text{silt}_1$$

where $\text{sand}_{1}$ is surface-layer `sand` (%), $\text{clay}_{1}$ is surface-layer [clay](clay.md) (%), and $\text{silt}_{1}$ is surface-layer [silt](silt.md) (%). Surface `sand` also enters the Green-Ampt wetting-front suction head ([`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L295)) and CENTURY microbial respiration efficiency ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L480-L483)).
