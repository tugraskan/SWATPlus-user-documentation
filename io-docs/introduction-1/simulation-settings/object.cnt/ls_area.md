---
description: Land area of the watershed in ha
---

# ls\_area

**Code reference:** `bsn%area_ls_ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L11)).

Land area of the watershed excluding ponds and reservoirs (`ha`; Fortran struct default: `0.`). Read in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38), this area is multiplied by each HRU's basin area fraction (`lsu_elem%bsn_frac`) when updating HRU areas in [`hru_fr_change.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L97) and soft-calibration region areas in [`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L108):

$$A_{\text{hru}} = f_{\text{bsn}} \times A_{\text{ls}}$$

where $A_{\text{hru}}$ is the HRU area (ha), $f_{\text{bsn}}$ is the HRU's basin area fraction, and $A_{\text{ls}}$ is `ls_area` (ha).
