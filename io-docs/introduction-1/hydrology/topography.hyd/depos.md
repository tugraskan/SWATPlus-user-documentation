---
description: Sediment transport capacity multiplier
---

# depos

**Code reference:** `topo_db(ith)%dep_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L11)).

Dimensionless multiplier $D$ for sediment transport capacity during surface runon across an HRU. The built-in topography record uses 1. In [`rls_routesurf.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rls_routesurf.f90#L56-L66), the capacity is

$$T = D\,C\,Q\,S^{1.4}W^{1.4}$$

where:

- $T$ is the sediment transport capacity,
- $D$ is `depos` (dimensionless),
- $C$ is the USLE cover factor (dimensionless),
- $Q$ is the surface runon term used in the calculation,
- $S$ is slope steepness (m/m), and
- $W$ is [field width](../field.fld/wd.md) (m).

Sediment above the capacity is deposited, so a larger coefficient allows more of the incoming sediment to pass through this step.
