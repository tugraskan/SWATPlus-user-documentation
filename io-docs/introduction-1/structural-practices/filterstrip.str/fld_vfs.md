---
description: Ratio of field area to filter strip area
---

# fld\_vfs

**Code reference:** `filtstrip_db(ifiltop)%vfsratio` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L33)).

Dimensionless ratio of the upslope field area to the total vegetative filter strip area (range `0.0–300.0`; values from `30–60` are most common). In [`smp_filter.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_filter.f90#L94-L95), SWAT+ uses `fld_vfs` to compute the surface areas of the outer 90% ($A_1$) and concentrated 10% ($A_2$) filter strip sections:

$$A_1 = \frac{0.9 \, A_{\text{hru}}}{R_{\text{vfs}}}, \qquad A_2 = \frac{0.1 \, A_{\text{hru}}}{R_{\text{vfs}}}$$

where $A_{\text{hru}}$ is HRU area (ha) and $R_{\text{vfs}}$ is `fld_vfs`. At runtime ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L58-L61)), values $\le 0$ are reset to `0.0` and values $> 300$ are capped at `300.0`.
