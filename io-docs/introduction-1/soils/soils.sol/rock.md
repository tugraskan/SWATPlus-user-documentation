---
description: Rock fragment content of the soil layer
---

# rock

**Code reference:** `soildb(isol)%ly(j)%rock` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L55)).

Percent by weight of the sample that has a particle diameter `> 2` mm (`%`; Fortran struct default: `0.0`), i.e., the fraction that does not pass through a 2 mm sieve. During initialization in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L80), values `> 98.0` are clamped to `98.0`.

Surface-layer `rock` reduces USLE/MUSLE erosion via the coarse-fragment factor in [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L78) and [`ero_ysed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ero_ysed.f90#L52):

$$f_{\text{rock}} = \exp(-0.053 \cdot \text{rock}_1)$$

where $f_{\text{rock}}$ is the coarse-fragment erosion factor (dimensionless) and $\text{rock}_{1}$ is surface-layer `rock` (%).

Across soil layers, $(1 - \text{rock}_{l} / 100)$ scales fine-earth soil mass in carbon and tillage mixing routines ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L314), [`mgt_biomix.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_biomix.f90#L203)).
