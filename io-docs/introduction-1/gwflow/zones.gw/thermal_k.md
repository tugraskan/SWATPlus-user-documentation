---
description: "Thermal conductivity, J/(day·m·°C)"
---

# thermal_K

**Code reference:** `zones_Kt(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L98), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L402)).

Thermal conductivity of the aquifer, in J/(day·m·°C), used only when `heat` is 1 in [codes.gw](../codes.gw/heat.md). It is an optional sixth column; a missing value or `null` gives 0 ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L401-L403)). Each cell takes the value of its `K_zone` (not its `Sy_zone`) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L459), [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1493)). Heat conduction between neighbors uses the harmonic mean of the two cells' values ([`gwflow_heat.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_heat.f90#L92-L94)).
