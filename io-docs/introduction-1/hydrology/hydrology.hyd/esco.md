---
description: Soil evaporation compensation factor
---

# esco

**Code reference:** `hyd_db(ithyd)%esco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L11)).

Dimensionless soil evaporation compensation factor. Larger values allow more evaporation to be drawn from deeper layers. In [`et_act.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_act.f90#L217-L226), potential extraction from a layer is:

$$E = E_z - E_{\mathrm{prev}}(1 - c)$$

where $E$ is the potential evaporative demand for the layer (mm), $E_z$ and $E_{\mathrm{prev}}$ are cumulative evaporative demands to the current and previous layer depths (mm), and $c$ is `esco` (dimensionless). The model then reduces the demand for dry soil.
