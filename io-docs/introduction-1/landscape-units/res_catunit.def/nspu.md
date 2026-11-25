---
description: "Number of element-list entries"
---

# nspu

**Code reference:** `nspu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L22), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L48)).

Number of integer tokens read into `elem_cnt(1:nspu)` on this row (`integer`, dimensionless, default `0`). When `nspu > 0`, [`res_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L59-L60) expands the list via [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L1-L96); when `nspu <= 0`, it falls back to all reservoirs `1..sp_ob%res` (`#L65-L67`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
