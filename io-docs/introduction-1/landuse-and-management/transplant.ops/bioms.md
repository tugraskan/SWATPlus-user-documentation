---
description: "Initial biomass"
---

# bioms

**Code reference:** `transpl(ic)%bioms` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L148), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_transplant_read.f90#L43)).

Initial dry plant biomass (`kg/ha`, struct default `0.0`) at transplanting. In [`mgt_transplant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L32), SWAT+ assigns `pl_mass(j)%tot(ipl)%m = bioms`, initializes total N mass ([`#L40`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L40)), and partitions the mass into root, seed, leaf, and stem pools ([`#L56-L58`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L56-L58)).
