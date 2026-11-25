---
description: "SWAT+ channel number"
---

# channel

**Code reference:** `channel` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L22), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L60)).

Number of the SWAT+ channel (`chandeg` object) in this cell. The channel supplies the width, the default depth and the water exchanged ([`gwflow_channel_exch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L45-L50)). SWAT+ does not check that the number is within the number of channels.
