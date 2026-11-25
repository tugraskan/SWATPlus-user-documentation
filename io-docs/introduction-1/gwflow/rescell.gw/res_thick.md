---
description: "Reservoir-bed thickness, m"
---

# res_thick

**Code reference:** `res_thick` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L287), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1117)).

Thickness of the reservoir bed, in m, for all reservoirs ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1117)). In the exchange formula it appears in both the gradient and the flow area, so it cancels: the value has no effect unless it is 0, which makes the division fail ([`gwflow_reservoir.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L64-L67)). This is listed in `MODEL_ISSUES.md`.
