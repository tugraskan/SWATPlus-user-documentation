---
description: "Daily rate at which biological mixing recovers after tillage"
---

# bio\_consf

**Code reference:** `bio_consf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L16), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L75), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L487-L488)).

Biological mixing consolidation factor. After a tillage operation, biological mixing of each layer restarts from 0 and [`mgt_biomix.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_biomix.f90#L133-L152) raises it each day by this fraction of the layer's initial biomixing efficiency, until it returns to that efficiency:

$$
b = \min\left(b + k \, b_{init}, \; b_{init}\right), \qquad k = k_{bio} \min\left(1, \frac{SW}{FC}\right)
$$

where:

- $b$ is the layer's current biological mixing efficiency (dimensionless),
- $b_{init}$ is the layer's initial biological mixing efficiency (dimensionless),
- $k$ is the daily recovery increment (1/day),
- $k_{bio}$ is `bio_consf` (fraction/day),
- $SW$ is the layer's soil water content (mm), and
- $FC$ is the layer's field capacity (mm).

A larger value lets mixing recover faster.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `bio_consol` and uses 0.15. The calibration parameter is `bio_consol`.
