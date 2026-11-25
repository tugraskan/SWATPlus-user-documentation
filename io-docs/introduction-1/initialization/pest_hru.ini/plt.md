---
description: Initial pesticide mass on plant foliage
---

# plt

**Code reference:** `pest_soil_ini(ipesti)%plt(ipest)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L292)).

Initial pesticide mass on plant foliage (`kg/ha`), read in [`pest_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_hru_aqu_read.f90#L59). Note that despite the generic struct comment (`ppm or #cfu/m^2`), [`pesticide_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_init.f90#L59-L68) assigns `plt` directly to the HRU plant pesticide balance (`hpestb_d(ihru)%pest(ipest)%plant`) and distributes it across active plants in the community by leaf-area-index (LAI) fraction:

$$M_{\text{pl},i} = f_{\text{pl},i} \cdot M_{\text{plt}}, \qquad f_{\text{pl},i} = \min\!\left(\frac{\text{LAI}_{i}}{\text{LAI}_{\text{sum}}},\, 1\right)$$

where:
* $M_{\text{pl},i}$ is initial pesticide mass on plant $i$ (`kg/ha`),
* $f_{\text{pl},i}$ is the LAI allocation fraction (set to `0` when total community LAI, `pcom(ihru)%lai_sum`, is zero),
* $M_{\text{plt}}$ is `plt` (`kg/ha`),
* $\text{LAI}_{i}$ is the leaf area index of plant $i$, and
* $\text{LAI}_{\text{sum}}$ is total community leaf area index (`pcom(ihru)%lai_sum`).
