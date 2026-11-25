---
description: "Depth subtracted from every channel-cell bed elevation"
---

# river_thresh

**Code reference:** `gw_bed_change` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L196), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L258)).

Depth, in m, subtracted from the bed elevation of every channel–cell connection before groundwater–channel exchange is computed ([`gwflow_channel_exch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L63)):

$$z_{b} = z_{\text{bed}} - d$$

where $z_{\text{bed}}$ is `bed_elev` from [chancell.gw](../chancell.gw/bed_elev.md) and $d$ is this value. A positive value lowers the channel beds and the channel stage, which favors groundwater discharge to channels. Despite the name, it is not a threshold. The calibration parameter `stream_bed` changes it ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1109-L1112)).

SWAT+ Editor writes this value from its `river_depth` setting, whose default is 5.0, so beds are lowered by 5 m unless that setting is changed. The name is listed in `EDITOR_RENAME_CANDIDATES.md`.
