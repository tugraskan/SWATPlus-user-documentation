---
description: "Specified pumping from pumpex.gw (1 = on)"
---

# pumpex

**Code reference:** `gw_pumpex_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L260), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L245)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on and [pumpex.gw](../pumpex.gw/README.md) exists, the pumping periods in that file are applied. If the file is missing, a message is written to the GWFlow record file and no pumping is simulated ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L952-L1016)). Irrigation pumping from groundwater does not depend on this setting.
