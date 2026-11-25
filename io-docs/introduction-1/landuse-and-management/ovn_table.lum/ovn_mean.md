---
description: Mean overland flow Manning’s n value
---

# ovn\_mean

**Code reference:** `overland_n(il)%ovn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L59), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/overland_n_read.f90#L44)).

Mean overland flow Manning's roughness coefficient $n_{\text{ov}}$ (dimensionless, default `0.5`). Assigned to `hru(iihru)%luse%ovn` in [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L387) and used in [`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L59-L68) (and routing-unit area weighting at [`#L31`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L31)) to compute HRU overland flow time of concentration $t_{\text{ov}}$ (`hr`):

$$t_{\text{ov}} = \frac{0.0556\,(L_{\text{slp}} \cdot n_{\text{ov}})^{0.6}}{(S + 0.0001)^{0.3}}$$

where $L_{\text{slp}}$ is HRU slope length (`m`) and $S$ is HRU slope (`m/m`). It also sets `ch_n` in the tributary-channel travel-time term ([`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L62-L67)). The [ovn\_min](ovn_min.md) and [ovn\_max](ovn_max.md) columns serve only as calibration-range guidance.
