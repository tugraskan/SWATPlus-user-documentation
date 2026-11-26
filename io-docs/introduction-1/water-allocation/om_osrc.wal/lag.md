---
description: "Large-aggregate concentration"
---

# lag

**Code reference:** `osrc_om(iom_osrc)%lag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L47), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L43)).

Large-aggregate concentration (`ppm`, equivalent to `mg/L` or `g/m^3`; Fortran struct default: `0.`). Converted to metric tons (`t`) in [`hydrograph_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1256):

$$M = \frac{C \cdot Q_{\text{out}}}{10^{6}}$$

where $C$ is `lag` (`ppm`), $Q_{\text{out}}$ is `outflo_om%flo` (`m^3`), and $M$ is the converted mass (`t`). On SWAT+ dev the withdrawal copies the record `osrc_om(j)`, sets its volume, and then converts this concentration to mass ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L53-L57)). Here `j` is the outside-source object number from [point_of_diver.wro](../point_of_diver.wro/README.md), so the record used is the one at that position in this file, not necessarily the one named for the source in [outside_src.wal](../outside_src.wal/README.md). (SWAT+ main reset the record before converting, so this value was not used.)
