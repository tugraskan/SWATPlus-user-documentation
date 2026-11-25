---
description: "Floodplain-bed hydraulic conductivity, m/day"
---

# gw_fp_K

**Code reference:** `gw_fp_K(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L310), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1192)).

Hydraulic conductivity of the floodplain bed, in m/day, used in the floodplain exchange calculation ([`gwflow_floodplain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_floodplain.f90#L60), [`gwflow_floodplain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_floodplain.f90#L76-L82)):

$$Q = \pm K \, A$$

where $Q$ is the floodplain exchange flow ($\text{m}^3/\text{day}$), $K$ is `gw_fp_K` (`m/day`), and $A$ is [gw_fp_area](gw_fp_area.md) ($\text{m}^2$).

The calibration parameter `floodplain_K` changes the value read here after it has been copied to the channel's floodplain list, so calibration has no effect ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1088-L1091)). This is listed in `MODEL_ISSUES.md`.
