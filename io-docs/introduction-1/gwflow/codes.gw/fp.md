---
description: "Floodplain exchange from floodplain.gw (1 = on)"
---

# fp

**Code reference:** `gw_fp_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L305), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L249)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on and [floodplain.gw](../floodplain.gw/README.md) exists, floodplain cells exchange water with a channel on days when the channel overtops its banks. If the file is missing, SWAT+ writes a message and sets the setting to 0 ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1176-L1231)).
