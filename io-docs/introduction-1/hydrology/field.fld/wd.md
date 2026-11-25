---
description: Representative field width
---

# wd

**Code reference:** `field_db(ith)%wid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L18)).

Representative field width $W$ in meters. The built-in field record uses 100 m. Where incoming surface runoff is routed across an HRU, [`rls_routesurf.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rls_routesurf.f90#L56-L66) uses the width in the sediment transport capacity equation.

$$T = D\,C\,Q\,S^{1.4}W^{1.4}$$

where:

- $T$ is the sediment transport capacity,
- $D$ is the [deposition coefficient](../topography.hyd/depos.md) (dimensionless),
- $C$ is the USLE cover factor (dimensionless),
- $Q$ is the surface runon term used in the calculation,
- $S$ is slope steepness (m/m), and
- $W$ is `wd` (m).
