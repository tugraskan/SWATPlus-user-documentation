---
description: "Effluent outflow fraction returned from water use"
---

# flo

**Code reference:** `wuse_om_efflu(iom_use)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_use_read.f90#L44)).

Dimensionless fraction of water-use inflow released as effluent (`fraction`; Fortran struct default: `0.`). In [`wallo_use.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L56), effluent volume is computed as:

$$Q_{\text{out}} = f_{\text{efflu}} \cdot V_{\text{stor}}$$

where $f_{\text{efflu}}$ is `wuse_om_efflu(iom)%flo` (`fraction`), $V_{\text{stor}}$ is `wuse_om_stor(iuse)%flo` (`m^3`), and $Q_{\text{out}}$ is `outflo_om%flo` (`m^3`).
