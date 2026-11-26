---
description: "Object number for the action"
---

# ob_num

**Code reference:** `dtbl_flo(i)%act(iac)%ob_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L19)).

Object number used by the action: the demand object or storage object for `wallo_dmd` (the place-of-use number for `irr_dmd`; 0 means the current POU on SWAT+ dev), the source HRU for `tileflo_control`, and the place-of-use number for `duty_reset`. For `fill_res`, `fill_wtow`, `fill_can`, and `tileflo_control`, 0 means the current object. `duty_fr` takes the source or receiver from [option](option.md) instead. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L201-L235) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L861-L866)
