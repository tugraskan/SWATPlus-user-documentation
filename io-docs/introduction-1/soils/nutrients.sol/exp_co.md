---
description: Depth coefficient to adjust nutrient concentrations for depth
---

# exp\_co

**Code reference:** `solt_db(isolt)%exp_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L15)).

Depth coefficient ($\text{mm}^{-1}$; Fortran struct default: `0.001`) used in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L58) to attenuate initial surface concentrations of nitrate and labile phosphorus with soil depth:

$$f_{\text{dep},l} = \exp(-k_{\text{exp}} \cdot d_l)$$

where $k_{\text{exp}}$ is `exp_co` ($\text{mm}^{-1}$) and $d_l$ is the depth to the bottom of soil layer $l$ (mm). If `exp_co > 0.005`, [`solt_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/solt_db_read.f90#L49) replaces it with `0.001`.
