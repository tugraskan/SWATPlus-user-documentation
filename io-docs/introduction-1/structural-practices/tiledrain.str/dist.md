---
description: Distance between two drain tubes or tiles
---

# dist

**Code reference:** `sdr(isdr)%dist` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L91)).

Enter the distance between adjacent drain tubes or tiles in millimetres (mm). SWAT+ uses this value directly with drain depth, drain radius, and soil-profile depth, which are also in millimetres; for example, an input value of 30 is treated as 30 mm, not 30 m.

In the DRAINMOD routine (`tiledrain = 1` in `codes.bsn`, [`swr_drains.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L205)), `dist` enters Hooghoudt's drainage flux equation:

$$q = \frac{4 \cdot 24 \cdot K_e \cdot m \cdot (2 d_e + m)}{L^2}$$

where $q$ is daily drainage flux (mm/day), $K_e$ is effective lateral saturated hydraulic conductivity (mm/hr), $m$ is midpoint water-table height above the drain (mm), $d_e$ is Hooghoudt equivalent depth (mm), and $L$ is `dist` (mm).
