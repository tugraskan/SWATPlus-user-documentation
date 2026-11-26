---
description: "Residue C:P ratio at which the phosphorus decomposition factor equals 1"
---

# cpr\_ref

**Code reference:** `cpr_ref` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L17), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L81), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L501-L502)).

Residue C:P ratio at which the phosphorus factor equals 1. Ratios above it slow decomposition.

[`cbn_surfrsd_decomp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_surfrsd_decomp.f90#L96-L112) reduces surface residue decomposition when the residue is poor in nitrogen or phosphorus:

$$
f_{CN} = \exp\left(-0.693 \, \frac{\min(CN, CN_{cap}) - CN_{ref}}{CN_{ref}}\right), \qquad f = \min(f_{CN}, f_{CP}, 1)
$$

where:

- $f_{CN}$ is the nitrogen decomposition factor (dimensionless),
- $CN$ is the residue C:N ratio (ratio),
- $CN_{cap}$ is [cnr\_cap](cnr_cap.md) (ratio),
- $CN_{ref}$ is [cnr\_ref](cnr_ref.md) (ratio),
- $f$ is the combined nutrient limitation factor (dimensionless), and
- $f_{CP}$ is the phosphorus decomposition factor, computed in the same way using the C:P ratio, [cpr\_cap](cpr_cap.md), and `cpr_ref`.

A factor is 1 when the residue holds almost no N or P. Only surface residue uses these values: the soil residue routine `cbn_rsd_decomp` is not called on SWAT+ main or dev (on main the call was commented out; dev removed it).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `cpr_ref` and uses 200.0. The calibration parameter is `cpr_ref`.
