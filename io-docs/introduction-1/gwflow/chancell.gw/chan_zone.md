---
description: "Zone for streambed properties"
---

# chan_zone

**Code reference:** `chan_zone` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L62)).

Zone number, that is the line position in [zones.gw](../zones.gw/README.md). The connection takes `streambed_K` and `streambed_thick` from this zone, unless [cells.gw](../cells.gw/README.md) has `strK` or `strthick` values for the cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L649-L657)).
