---
description: "Water available from this outside source record (m3/s on SWAT+ dev)"
---

# flo

**Code reference:** `osrc_om(iom_osrc)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L43)).

Water available from this outside-source record (Fortran struct default: `0.`). On SWAT+ dev the withdrawal treats it as a rate in `m^3/s` and converts it to a daily volume ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L53-L57)):

$$Q_{\text{out}} = f_{\text{pod}} \cdot Q_{\text{osrc}} \cdot 86400$$

where $f_{\text{pod}}$ is the POD fraction `pou(ipou)%pod(pod_num)%frac`, $Q_{\text{osrc}}$ is `osrc_om(j)%flo` (`m^3/s`), $j$ is the outside-source object number, and $Q_{\text{out}}$ is `outflo_om%flo` (`m^3`). The whole `osrc_om(j)%flo` is added to `osrc(j)%wdraw` on each withdrawal. (SWAT+ main used this value as a daily volume without the 86,400 factor.) Note that [`hydrograph_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1239) leaves `flo` unscaled (`* 86400.` is commented out).
