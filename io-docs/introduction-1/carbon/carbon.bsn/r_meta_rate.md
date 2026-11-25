---
description: "Daily transformation rate of the metabolic litter pool"
---

# r\_meta\_rate

**Code reference:** `carbdb(layer_id)%meta_rate` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L67), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L147), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L518-L519)).

Maximum daily fraction of metabolic litter carbon transformed under optimal conditions ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L507-L511)). Row `1` applies to soil layer 1, the 10 mm surface layer, and row `2` to all deeper layers ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L317-L324)).

$$
\Delta C = k \, f_c \, C_{pool}, \qquad f_c = \min\left(15, \; 0.9 \sqrt{f_T f_W} \, f_O \, f_{till}\right)
$$

where:

- $\Delta C$ is the daily transformed metabolic litter carbon (kg/ha/day),
- $k$ is `r_meta_rate` (1/day),
- $f_c$ is the combined environmental factor (dimensionless; [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L429)),
- $C_{pool}$ is the metabolic litter pool carbon (kg/ha),
- $f_T$ is the soil temperature factor ([tmpf](tmpf.md), dimensionless),
- $f_W$ is the soil water factor ([watf](watf.md), dimensionless),
- $f_O$ is the depth (oxygen) factor (dimensionless), and
- $f_{till}$ is the tillage factor (dimensionless).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `meta_rate` and uses 0.0405 and 0.0507 for rows 1 and 2. The calibration parameter is `meta_rate` (by layer).
