---
description: "Wetland-bed thickness, m"
---

# thick_val

**Code reference:** `thick_val` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L22), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L84)).

Thickness of the wetland bed, in m. It is $b$ in the exchange formula on the [file page](README.md) ([`gwflow_wetland.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L72), [`gwflow_wetland.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L127-L130)). For seepage from the wetland, a value of 0 or less is replaced by 0.10 m; for inflow to the wetland, 0 makes the division fail.
