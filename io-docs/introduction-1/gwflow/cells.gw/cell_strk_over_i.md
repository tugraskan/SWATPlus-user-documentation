---
description: "Streambed conductivity for channels in this cell, m/day"
---

# cell_strK_over(i)

**Code reference:** `cell_strK_over(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L193), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L467-L470)).

Optional column 15. Streambed hydraulic conductivity, in m/day, for every channel connection in this cell. It replaces `streambed_K` of the connection's `chan_zone` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L651-L654)). It has no effect on cells without a line in [chancell.gw](../chancell.gw/README.md).
