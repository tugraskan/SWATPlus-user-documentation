---
description: "Channel depth by depth zone, m"
---

# depth_by_zone

**Code reference:** `gw_chan_dep(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L201), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L580)).

Depth of water in the channel, in m, one value per depth zone, in zone order. The number of values per line is the largest `dep_zone` in [chancell.gw](../chancell.gw/dep_zone.md) ([`gwflow_chan_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L92-L93)). Each connection uses the value of its zone as $D$ in the exchange formula on [bed_elev](../chancell.gw/bed_elev.md) ([`gwflow_channel_exch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L68-L71)).
