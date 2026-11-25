---
description: Object ID
---

# obj\_num

**Code reference:** `dtbl_lum(i)%act(iac)%ob_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L19)).

For most field actions, the number of the HRU acted on; 0 means the current object that triggered the table, not all objects. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L454-L456)

Some actions read it differently. `irrigate` takes the source object number here and always irrigates the current HRU, so give a positive number with `aqu`, `cha`, `sdc`, or `res`. `manure_demand` takes the manure source number, `res_irr_dmd` the reservoir number, and `fert_future` a future-fertilizer slot. [`actions.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/actions.f90#L241-L265) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L112-L122) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L424-L427)
