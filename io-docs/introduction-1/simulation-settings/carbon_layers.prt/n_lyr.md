---
description: "Count of carbon soil layers to be read for the simulation"
---

# n\_lyr

**Code reference:** `n_lyr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_layers_read.f90#L23)), stored into `cb_n_layers` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L23)).

Dimensionless integer specifying the fixed number of soil layers written in wide per-layer carbon output files (`hru_cbn_lyr_*`, `hru_cpool_stat_*`, `hru_n_p_pool_stat_*`, `hru_cflux_stat_*`, `hru_carb_drv_*`, `hru_carb_dyn_*`, and `hru_soil_snap_*`).

During reading in [`carbon_layers_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_layers_read.f90#L40-L46), if `n_lyr < 1`, SWAT+ writes a warning to `diagnostics.out`, keeps the fallback `cb_n_layers = 7`, and leaves `cb_n_layers_explicit = .false.`; otherwise it sets `cb_n_layers = n_lyr` and `cb_n_layers_explicit = .true.`. When `carbon_layers.prt` is absent or rejected, [`output_landscape_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L26-L32) defaults `cb_n_layers` to the largest soil layer count across all HRUs (falling back to `7` if $< 1$):

$$N_{\text{lyr}} = \max_{j} n_{\text{ly},j}$$

where $N_{\text{lyr}}$ is `cb_n_layers` and $n_{\text{ly},j}$ is the soil layer count of HRU $j$. Output writers iterate up to $\min(N_{\text{lyr}}, n_{\text{use}})$ per HRU and pad missing trailing layers with `-99.0` ([`carbon_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L590-L703), [`soil_nutcarb_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L298), [`soil_carbvar_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_carbvar_write.f90#L47)).
