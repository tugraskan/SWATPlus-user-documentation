---
description: Representative field length
---

# len

**Code reference:** `field_db(ith)%length` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L17)).

Representative field length in meters. The built-in field record uses 500 m. For a routing unit, [`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L42-L51) converts this length to kilometers before computing the channel travel time:

$$t_c = \frac{0.62 \, (L/1000) \, n^{0.75}}{A^{0.125} \, S^{0.375}}$$

where:

- $t_c$ is the channel travel time (h),
- $L$ is `len` (m),
- $n$ is Manning's roughness coefficient (dimensionless),
- $A$ is drainage area (km²), and
- $S$ is the channel slope used for this calculation (m/m).

HRU time of concentration uses an area-derived length. [`time_conc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_conc_init.f90#L55-L68)
