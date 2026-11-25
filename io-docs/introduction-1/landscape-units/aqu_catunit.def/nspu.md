---
description: "Number of element-list entries"
---

# nspu

**Code reference:** `nspu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L22), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L55)).

Number of integer tokens read into `elem_cnt(1:nspu)` on this row (`integer`, dimensionless, default `0`). When `nspu > 0`, [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L66-L110) expands the list via [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L1-L96); when `nspu <= 0`, it falls back to `1..sp_ob%hru` in `acu_out` (`#L72-L74`) and `1..sp_ob%aqu` (sized by `sp_ob%hru` at `#L115-L117`) in `acu_reg`.

Note that `acu_out` is never read and `acu_reg` only populates `acu_cal` ([`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L184-L188)), which is also unused in simulation calculations.
