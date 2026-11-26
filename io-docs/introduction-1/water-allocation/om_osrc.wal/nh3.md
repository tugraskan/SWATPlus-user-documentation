---
description: "Ammonia-nitrogen concentration"
---

# nh3

**Code reference:** `osrc_om(iom_osrc)%nh3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L39), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L43)).

Ammonia-nitrogen concentration (`ppm`, equivalent to `mg/L` or `g/m^3`; Fortran struct default: `0.`). Converted to `kg N` in [`hydrograph_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1248):

$$M = \frac{C \cdot Q_{\text{out}}}{1000}$$

where $C$ is `nh3` (`ppm`), $Q_{\text{out}}$ is `outflo_om%flo` (`m^3`), and $M$ is the converted mass (`kg N`). On SWAT+ dev the withdrawal copies the record `osrc_om(j)`, sets its volume, and then converts this concentration to mass ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L53-L57)). Here `j` is the outside-source object number from [point_of_diver.wro](../point_of_diver.wro/README.md), so the record used is the one at that position in this file, not necessarily the one named for the source in [outside_src.wal](../outside_src.wal/README.md). (SWAT+ main reset the record before converting, so this value was not used.)
