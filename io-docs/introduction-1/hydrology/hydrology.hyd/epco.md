---
description: Plant uptake compensation factor
---

# epco

**Code reference:** `hyd_db(ithyd)%epco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L12)).

Dimensionless plant water uptake compensation factor. [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L359-L364) copies the HRU value to each crop. A larger value lets deeper layers compensate more for unmet uptake in upper layers. For layers other than the second layer, [`pl_waterup.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_waterup.f90#L122-L138) computes:

$$U = U_{\mathrm{cum}} - U_{\mathrm{prev}}(1 - c)$$

where $U$ is the layer potential water uptake (mm), $U_{\mathrm{cum}}$ is the cumulative potential uptake to the current layer depth (mm), $U_{\mathrm{prev}}$ is the previous cumulative potential uptake (mm), and $c$ is `epco` (dimensionless). The second layer uses $U_{\mathrm{cum}}$, equivalent to $c = 1$ for this calculation. Soil water availability limits uptake.
