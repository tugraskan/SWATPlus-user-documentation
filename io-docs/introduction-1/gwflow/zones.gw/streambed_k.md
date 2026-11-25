---
description: "Streambed hydraulic conductivity, m/day"
---

# streambed_K

**Code reference:** `zones_strK(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L96), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L399)).

Hydraulic conductivity of the streambed, in m/day. Each channel–cell connection in [chancell.gw](../chancell.gw/README.md) takes the value of its `chan_zone`, unless the cell has a `strK` value in [cells.gw](../cells.gw/cell_strk_over_i.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L649-L657)). It sets the exchange rate with the channel; see [bed_elev](../chancell.gw/bed_elev.md) for the formula. The calibration parameter `stream_K` changes it channel by channel ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1094-L1099)).
