---
description: "Element-list entry"
---

# elem\_cnt

**Code reference:** `elem_cnt(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L54)).

List of `nspu` integers specifying element IDs (and optional negative-end inclusive ranges `start -end`) referencing [`rec_catunit.ele`](../rec_catunit.ele/README.md) (`integer`, dimensionless), expanded via [`define_unit_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/define_unit_elements.f90#L1-L96) into `pcu_out(i)%num` and `pcu_out(i)%num_tot` ([`rec_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L60-L61)).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
