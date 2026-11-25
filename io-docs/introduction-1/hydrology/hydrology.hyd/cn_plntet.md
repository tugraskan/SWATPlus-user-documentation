---
description: Lateral flow coefficient
---

# latq\_co

**Code reference:** `hyd_db(ithyd)%latq_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L51)).

Dimensionless multiplier $c_{\ell}$ for lateral soil flow. The built-in hydrology record uses 0.3. Below the top soil layer, [`swr_percmicro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmicro.f90#L60-L73) calculates:

$$q_{\ell} = \frac{0.024 \, c_{\ell} H K S}{L}$$

where:

- $q_{\ell}$ is the layer lateral flow (mm),
- $c_{\ell}$ is `latq_co` (dimensionless),
- $H$ is saturated thickness,
- $K$ is saturated hydraulic conductivity (mm/h),
- $S$ is slope steepness (m/m), and
- $L$ is [lateral slope length](../topography.hyd/lat_len.md) (m).

It bounds the result between zero and the layer's excess water. The top layer produces zero in this calculation.
