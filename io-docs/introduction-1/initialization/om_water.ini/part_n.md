---
description: Organic N
---

# part\_n

**Code reference:** `om_init_water(ichi)%orgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L34)).

Initial organic nitrogen concentration in water (`ppm`, equivalent to `mg/L` or `g/m^3`; default `0`). SWAT+ converts this concentration to stored mass (`kg N`) using the initialized water volume $V_{\text{init}}$ (`m^3`) in [`res_convert_mass`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1291) (reservoirs and wetlands) and [`hyd_convert_conc_to_mass`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1243) (SWAT-DEG channels):

$$M = \frac{C \cdot V_{\text{init}}}{1000}$$

where $M$ is initial stored mass (`kg N`), $C$ is `part_n` (`ppm`), and $V_{\text{init}}$ is initial water volume (`m^3`).
