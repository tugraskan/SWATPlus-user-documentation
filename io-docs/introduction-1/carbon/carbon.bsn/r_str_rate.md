---
description: "Daily transformation rate of the structural litter pool"
---

# r\_str\_rate

**Code reference:** `carbdb(layer_id)%str_rate` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L68), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L148), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L520-L521)).

Maximum daily fraction of structural litter carbon transformed under optimal conditions. [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L500-L505) also multiplies it by $e^{-3 L}$, where $L$ is the lignin fraction of the structural litter (at most 0.8). Row `1` applies to soil layer 1, the 10 mm surface layer, and row `2` to all deeper layers ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L317-L324)).

$$
\Delta C = k \, f_c \, C_{pool}, \qquad f_c = \min\left(15, \; 0.9 \sqrt{f_T f_W} \, f_O \, f_{till}\right)
$$

where:

- $\Delta C$ is the daily transformed structural litter carbon (kg/ha/day),
- $k$ is `r_str_rate` multiplied by $e^{-3 L}$ (1/day),
- $f_c$ is the combined environmental factor (dimensionless; [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L429)),
- $C_{pool}$ is the structural litter pool carbon (kg/ha),
- $f_T$ is the soil temperature factor ([tmpf](tmpf.md), dimensionless),
- $f_W$ is the soil water factor ([watf](watf.md), dimensionless),
- $f_O$ is the depth (oxygen) factor (dimensionless), and
- $f_{till}$ is the tillage factor (dimensionless).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `str_rate` and uses 0.0107 and 0.0134 for rows 1 and 2. The calibration parameter is `str_rate` (by layer).
