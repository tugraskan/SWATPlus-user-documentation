---
description: "Land-to-aquifer connection: 1 = HRU cells, 2 = LSU cells"
---

# conn_type

**Code reference:** `conn_type` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L28), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L242)).

Chooses how recharge and groundwater ET are mapped between land units and cells ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L327-L368)):

* **1:** HRU–cell links from [hrucell.gw](../hrucell.gw/README.md). If that file is missing, [lsucell.gw](../lsucell.gw/README.md) is used instead.
* **2:** LSU–cell links from `lsucell.gw`. If that file is missing, `hrucell.gw` is used instead.

With LSU links, `gw_soil` and `wet` are set to 0, because those transfers need HRU links. Any other value writes "neither gwflow.hrucell or gwflow.lsucell found" to the GWFlow record file and stops the run. If both files are missing, the run does not stop; the HRU reader then finds no links, so no recharge reaches the aquifer. This is listed in `MODEL_ISSUES.md`.
