---
description: "Ratio of soluble carbon concentration in runoff and lateral flow to that in percolate"
---

# prmt\_44

**Code reference:** `cb_wtr_coef%prmt_44` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L147), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L73), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L483-L484)).

Splits the microbial carbon lost from soil layer 1 (see [prmt\_21](prmt_21.md)) between percolation and the horizontal flows ([`nut_orgnc2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_orgnc2.f90#L130-L136)):

$$
c_{perc} = \frac{C_{loss}}{Q_{perc} + r \, (Q_{surf} + Q_{lat})}, \qquad c_{surf} = r \, c_{perc}
$$

where:

- $c_{perc}$ is the soluble carbon concentration in percolate (kg/ha/mm),
- $c_{surf}$ is the soluble carbon concentration in surface runoff and lateral flow (kg/ha/mm),
- $C_{loss}$ is the microbial carbon lost from layer 1 (kg/ha),
- $Q_{perc}$ is the day's percolation (mm),
- $Q_{surf}$ is the day's surface runoff (mm),
- $Q_{lat}$ is the day's lateral flow (mm), and
- $r$ is `prmt_44` (ratio).

The source comment gives a range of 0.1 to 1.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `solc_ratio` and uses 0.5. The calibration parameter is `solc_ratio`.
