---
description: "HRU changed by the action"
---

# ob_num

**Code reference:** `dtbl_scen(i)%act(iac)%ob_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L19)).

HRU number the action changes. 0 means the HRU currently being processed by the daily update, which is the usual entry. A positive number applies the change to that HRU each time any HRU satisfies the conditions. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1009-L1011) · [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L218-L226)
