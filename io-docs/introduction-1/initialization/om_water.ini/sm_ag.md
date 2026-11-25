---
description: Detached small aggregates
---

# sag

**Code reference:** `om_init_water(ichi)%sag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L46)).

Initial detached small-aggregate concentration in water (`ppm`, equivalent to `mg/L` or `g/m^3`; default `0`). SWAT+ converts this concentration to stored mass (`metric tons`) using the initialized water volume $V_{\text{init}}$ (`m^3`) in [`res_convert_mass`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1303) (reservoirs and wetlands) and [`hyd_convert_conc_to_mass`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1255) (SWAT-DEG channels):

$$M = \frac{C \cdot V_{\text{init}}}{10^{6}}$$

where $M$ is initial stored mass (`metric tons`), $C$ is `sag` (`ppm`), and $V_{\text{init}}$ is initial water volume (`m^3`).
