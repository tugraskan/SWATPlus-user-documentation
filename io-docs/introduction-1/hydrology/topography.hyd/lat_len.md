---
description: Slope length for lateral subsurface flow
---

# lat\_len

**Code reference:** `topo_db(ith)%lat_len` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L9)).

Slope length $L$ for lateral subsurface flow in meters. [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L37-L38) substitutes 50 m for values below $10^{-6}$ m during HRU initialization.

In [`swr_percmicro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmicro.f90#L60-L73), layer lateral flow is calculated as:

$$q_{\ell} = \frac{0.024 \, c_{\ell} H K S}{L}$$

where:

- $q_{\ell}$ is the layer lateral flow (mm),
- $c_{\ell}$ is the lateral flow coefficient (dimensionless),
- $H$ is saturated thickness,
- $K$ is saturated hydraulic conductivity (mm/h),
- $S$ is slope steepness (m/m), and
- $L$ is `lat_len` (m).

The top layer produces zero lateral flow in this calculation, and other layers are limited to their excess water. $L$ also enters the estimated [lateral flow travel time](../hydrology.hyd/lat_time.md).
