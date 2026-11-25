---
description: "Storage retention multiplier after evaporation"
---

# evap_co

**Code reference:** `canal(ic)%evap_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L204), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L46,L55)).

Evaporation retention multiplier applied directly to canal water storage (`fraction`). In [`wallo_canal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L31), SWAT+ updates stored volume as:

$$V_{\text{stor}} \leftarrow e_{\text{co}} \cdot V_{\text{stor}}$$

where $e_{\text{co}}$ is `canal(ican)%evap_co` and $V_{\text{stor}}$ is `canal_om_stor(ican)%flo` (`m^3`). A value of `1.0` retains all stored water (no evaporative loss), whereas `0.0` removes all stored water.
