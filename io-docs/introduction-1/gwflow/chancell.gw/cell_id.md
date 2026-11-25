---
description: "Groundwater cell number"
---

# cell_id

**Code reference:** `cell_id` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L21), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L58)).

Number of the groundwater cell the channel crosses. Exchange is computed only when the cell is active (`stat` = 1) ([`gwflow_channel_exch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L56-L59)). With `grid_type` = `structured`, SWAT+ maps cell numbers through an identity list, so structured and unstructured grids both use cell numbers 1 to `ncell` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L313-L319)).
