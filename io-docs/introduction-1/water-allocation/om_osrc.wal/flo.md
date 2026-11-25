---
description: "Daily available water volume for this outside source record"
---

# flo

**Code reference:** `osrc_om(iom_osrc)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L43)).

Daily available water volume for this outside-source record (`m^3/day`; Fortran struct default: `0.`). During withdrawal in [`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_withdraw.f90#L53-L57), SWAT+ withdraws a fraction of this daily supply:

$$Q_{\text{out}} = f_{\text{pod}} \cdot Q_{\text{osrc}}$$

where $f_{\text{pod}}$ is `pou(pou_num)%pod(pod_num)%frac`, $Q_{\text{osrc}}$ is `osrc_om(j)%flo` (`m^3/day`), and $Q_{\text{out}}$ is `outflo_om%flo` (`m^3/day`). The unwithdrawn portion $(1 - f_{\text{pod}}) \cdot Q_{\text{osrc}}$ is added to `osrc(j)%wdraw`. Note that [`hydrograph_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1239) leaves `flo` unscaled (`* 86400.` is commented out).
