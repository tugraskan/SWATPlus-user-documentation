---
description: "HRU number for the j-th member"
---

# hru_num(j)

**Code reference:** `hruirr_db(irr)%hru_num(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L61), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L45)).

1-based HRU number for the j-th irrigated HRU in the group. Copied into `pou(ipou)%irr%hru(ihru)` in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L129), and used in [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_start_day.f90#L137-L145) to sum daily irrigation demand (`m^3`):

$$D_{\text{pou}} \leftarrow D_{\text{pou}} + d_{\text{irr}} \cdot A_{\text{hru}} \cdot 10$$

where $d_{\text{irr}}$ is `irrig(j)%demand` and $A_{\text{hru}}$ is HRU area (`ha`), and in [`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_pou_deliv.f90#L38-L85) to deliver irrigation to each HRU.
