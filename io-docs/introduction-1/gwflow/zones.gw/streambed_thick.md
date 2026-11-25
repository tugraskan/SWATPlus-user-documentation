---
description: "Streambed thickness, m"
---

# streambed_thick

**Code reference:** `zones_strbed(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L97), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L400)).

Thickness of the streambed, in m. Each channel–cell connection takes the value of its `chan_zone`, unless the cell has a `strthick` value in [cells.gw](../cells.gw/cell_strthick_over_i.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L649-L657)). The exchange rate is inversely proportional to it; see [bed_elev](../chancell.gw/bed_elev.md). A zero value makes the exchange divide by zero. The calibration parameter `stream_thk` changes it channel by channel ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1101-L1106)).
