---
description: "Column of chan_depth.gw for this connection"
---

# dep_zone

**Code reference:** `dep_zone` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L24), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L65)).

Optional sixth field. When [chan_depth.gw](../chan_depth.gw/README.md) exists, the connection takes its channel depth from this depth column of that file instead of the channel's `chd` ([`gwflow_channel_exch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L68-L70)). The number of depth columns is the largest `dep_zone` in this file ([`gwflow_chan_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L92)). With `chan_depth.gw` present, every connection needs a value of 1 or more; 0 points outside the depth list. Without `chan_depth.gw`, the value is not used.
