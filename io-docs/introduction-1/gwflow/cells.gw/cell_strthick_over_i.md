---
description: "Streambed thickness for channels in this cell, m"
---

# cell_strthick_over(i)

**Code reference:** `cell_strthick_over(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L193), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L471-L474)).

Optional column 16. Streambed thickness, in m, for every channel connection in this cell. It replaces `streambed_thick` of the connection's `chan_zone` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L655-L657)). It has no effect on cells without a line in [chancell.gw](../chancell.gw/README.md).
