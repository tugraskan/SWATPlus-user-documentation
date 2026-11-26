---
description: "HRU number for the j-th member"
---

# hru_num(j)

**Code reference:** `hruirr_db(irr)%hru_num(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L61), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L45)).

1-based HRU number for the j-th irrigated HRU in the group. Copied into `pou(ipou)%irr%hru(ihru)` in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L129), and used in [`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L41-L101) to sum the POU's daily irrigation demand and deliver irrigation to each HRU. On SWAT+ dev the HRU demand (`m^3`) is set by the `irr_wallo` decision-table action ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L256-L260)):

$$d_{\text{hru}} = I \cdot A_{\text{hru}} \cdot 10$$

where $I$ is the irrigation depth from the action (`mm`) and $A_{\text{hru}}$ is HRU area (`ha`). An HRU is supplied only while the summed demand is below `rate_max × 86400` and its demand is below the water still available; see [the allocation page](../../../swat+-output-files/water-allocation/allocation-transactions.md#daily-duty-and-reported-delivery).
