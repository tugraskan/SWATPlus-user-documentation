---
description: "Treated outflow fraction retained after treatment"
---

# flo

**Code reference:** `wtp_om_treat(iom_tr)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_treat_read.f90#L43)).

Dimensionless fraction of stored treatment-plant water released as treated outflow (`fraction`; Fortran struct default: `0.`). In [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L68), outflow to each point of return (POR) is computed as:

$$Q_{\text{out}} = V_{\text{stor}} \cdot f_{\text{treat}} \cdot f_{\text{por}}$$

where $V_{\text{stor}}$ is `wtp_om_stor(iwtp)%flo` (`m^3`), $f_{\text{treat}}$ is `wtp_om_treat(iom)%flo` (`fraction`), $f_{\text{por}}$ is `pou(ipou)%por(ipor)%frac`, and $Q_{\text{out}}$ is `outflo_om%flo` (`m^3`), capped by stored POR flow via [`hydrograph_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1265).
