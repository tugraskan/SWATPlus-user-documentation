---
description: "Residue C:N ratio at which the nitrogen decomposition factor equals 1"
---

# cnr\_ref

**Code reference:** `cnr_ref` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L15), [read](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/carbon_bsn_read.f90#L80), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L497-L498)).

Residue C:N ratio at which the nitrogen factor equals 1. Ratios above it slow decomposition.

[`cbn_surfrsd_decomp.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cbn_surfrsd_decomp.f90#L99-L115) reduces surface residue decomposition when the residue is poor in nitrogen or phosphorus:

$$
f_{CN} = \exp\left(-0.693 \, \frac{\min(CN, CN_{cap}) - CN_{ref}}{CN_{ref}}\right), \qquad f = \min(f_{CN}, f_{CP}, 1)
$$

where:

- $f_{CN}$ is the nitrogen decomposition factor (dimensionless),
- $CN$ is the residue C:N ratio (ratio),
- $CN_{cap}$ is [cnr\_cap](cnr_cap.md) (ratio),
- $CN_{ref}$ is `cnr_ref` (ratio),
- $f$ is the combined nutrient limitation factor (dimensionless), and
- $f_{CP}$ is the phosphorus decomposition factor, computed in the same way using the C:P ratio, [cpr\_cap](cpr_cap.md), and [cpr\_ref](cpr_ref.md).

A factor is 1 when the residue holds almost no N or P. Only surface residue uses these values: the call to the soil residue routine `cbn_rsd_decomp` is commented out ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_control.f90#L399)).

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `cnr_ref` and uses 25.0. The calibration parameter is `cnr_ref`.
