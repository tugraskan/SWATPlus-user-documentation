---
description: Volume of water
---

# vol

**Code reference:** `om_init_water(ichi)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Dimensionless initial water volume or depth fraction (`fraction`, default `0`). For reservoirs ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L100-L101)) and wetlands ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L155-L156)), [`res_convert_mass`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1289) multiplies `vol` by the principal volume to obtain initial water volume (`m^3`):

$$V_{\text{init}} = f_{\text{vol}} \cdot V_{\text{pvol}}$$

where $V_{\text{init}}$ is initial water volume (`m^3`), $f_{\text{vol}}$ is `vol` (`fraction`), and $V_{\text{pvol}}$ is principal storage volume (`m^3`).

For SWAT-DEG channels ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L217-L247)), `vol` scales bankfull channel depth to interpolate the channel rating curve (`rcurv_interp_dep`) for total initial storage `tot_stor(ich)%flo` (`rcurv%vol`):

$$d_{\text{init}} = f_{\text{vol}} \cdot d_{\text{ch}}$$

where $d_{\text{init}}$ is initial water depth (`m`), $f_{\text{vol}}$ is `vol` (`fraction`), and $d_{\text{ch}}$ is bankfull channel depth (`m`). When $f_{\text{vol}} \le 1.0$, all initial storage is placed in `ch_stor`; when $f_{\text{vol}} > 1.0$, storage is partitioned between `ch_stor` and floodplain storage `fp_stor`.
