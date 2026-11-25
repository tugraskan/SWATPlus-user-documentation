---
description: "Volume to divert to each pond, m³"
---

# div

**Code reference:** `gw_pond_info(r)%div` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L414), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L57)).

Volume to divert into each pond that day, in m³, one value per pond in [ponds.gw](../ponds.gw/README.md) order ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L57)). It is taken from the pond's source; channel and canal sources may supply less ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L82-L99)). Before a pond's start day its value is not used.
