---
description: "Daily transformation rate of the microbial pool in soil layer 1"
---

# r\_microb\_top\_rate

**Code reference:** `carbdb(layer_id)%microb_top_rate` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L69), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L149), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L522-L523)).

Maximum daily fraction of microbial carbon transformed under optimal conditions in soil layer 1 ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L513-L518)). Deeper layers use [r\_microb\_rate](r_microb_rate.md), so this value has no effect on row `2`. Row `1` applies to soil layer 1, the 10 mm surface layer, and row `2` to all deeper layers ([`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L317-L324)).

$$
\Delta C = k \, f_c \, C_{pool}, \qquad f_c = \min\left(15, \; 0.9 \sqrt{f_T f_W} \, f_O \, f_{till}\right)
$$

where:

- $\Delta C$ is the daily transformed microbial carbon in layer 1 (kg/ha/day),
- $k$ is `r_microb_top_rate` (1/day),
- $f_c$ is the combined environmental factor (dimensionless; [`cbn_zhang2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L429)),
- $C_{pool}$ is the microbial pool carbon (kg/ha),
- $f_T$ is the soil temperature factor ([tmpf](tmpf.md), dimensionless),
- $f_W$ is the soil water factor ([watf](watf.md), dimensionless),
- $f_O$ is the depth (oxygen) factor (dimensionless), and
- $f_{till}$ is the tillage factor (dimensionless).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `microb_top_rate` and uses 0.0164 and 0.02 for rows 1 and 2. The calibration parameter is `microb_top_rate` (by layer).
