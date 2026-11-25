---
description: Snowmelt factor near December 21
---

# melt\_min

**Code reference:** `snodb(isno)%meltmn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L77)).

Seasonal melt coefficient $b_D$ near December 21. The built-in snow record uses 0.5 mm water equivalent per day per °C. Use with [melt_max](melt_max.md).

The seasonal factor in [`sq_snom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_snom.f90#L63-L67) is:

$$b(d) = \frac{b_J + b_D}{2} + \sin\left(\frac{d - 81}{58.09}\right) \frac{b_J - b_D}{2}$$

where $b(d)$ is the seasonal melt factor (mm water equivalent per day per °C), $b_J$ is [melt\_max](melt_max.md) (mm water equivalent per day per °C), $b_D$ is `melt_min` (mm water equivalent per day per °C), and $d$ is day of year. The equation uses the same calendar phase in both hemispheres.
