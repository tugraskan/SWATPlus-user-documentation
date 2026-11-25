---
description: Lateral flow travel time
---

# lat\_ttime

**Code reference:** `hyd_db(ithyd)%lat_ttime` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L8)).

Lateral flow travel time $\tau$ in days. For a nonpositive input, [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L129-L145) estimates:

$$\tau = \max\left(1, \; \frac{10.4 \, L}{K_{\max}}\right)$$

where $\tau$ is the lateral flow travel time (days), $L$ is [lateral slope length](../topography.hyd/lat_len.md) (m), and $K_{\max}$ is the highest layer saturated hydraulic conductivity (mm/h).

The model stores a daily release fraction and releases fraction $f$ of stored lateral water and nitrate each day:

$$f = 1 - \exp(-1/\tau)$$

where $f$ is the daily lateral-flow release fraction (dimensionless) and $\tau$ is the lateral flow travel time (days). Tile drainage uses a separate lag. [`swr_substor.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_substor.f90#L52-L64)
