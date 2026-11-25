---
description: "Partition coefficient (Koc) for microbial carbon loss from the top soil layer with water"
---

# prmt\_21

**Code reference:** `cb_wtr_coef%prmt_21` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_module.f90#L146), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L73), [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L481-L482)).

Organic carbon partition coefficient $K_{oc}$ that controls how much microbial carbon leaves soil layer 1 with surface runoff, lateral flow and percolation each day ([`nut_orgnc2.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_orgnc2.f90#L118-L136)):

$$
C_{loss} = C_{mic} \left(1 - \exp\left(\frac{-Q}{SAT + 10^{-4} \, K_{oc} \, C_{tot}}\right)\right)
$$

where:

- $C_{loss}$ is the microbial carbon lost from soil layer 1 (kg/ha),
- $C_{mic}$ is the microbial carbon in layer 1 (kg/ha),
- $Q$ is the sum of surface runoff, lateral flow, and percolation (mm),
- $SAT$ is the layer's saturated water content (mm),
- $K_{oc}$ is `prmt_21` (partition coefficient), and
- $C_{tot}$ is the layer's total organic carbon (kg/ha).

A larger value holds more carbon in the soil. The source comment gives a range of 500 to 1500.

The SWAT+ example file (`refdata/Ames_sub1`) heads this column `koc_c` and uses 1000. The calibration parameter is `koc_c`.
