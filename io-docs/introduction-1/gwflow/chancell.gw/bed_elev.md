---
description: "Channel bed elevation in the cell, m"
---

# bed_elev

**Code reference:** `bed_elev` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L27), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chan_read.f90#L59)).

Elevation of the channel bed in this cell, in m. SWAT+ lowers it by `river_thresh` from [codes.gw](../codes.gw/river_thresh.md) and adds the channel depth to get the stage ([`gwflow_channel_exch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L61-L87)):

$$z_{b} = z_{\text{bed}} - d_{r}, \qquad H = z_{b} + D$$

where:
- $z_{b}$ is the adjusted channel bed elevation (m),
- $z_{\text{bed}}$ is `bed_elev` (m),
- $d_{r}$ is `river_thresh` from [codes.gw](../codes.gw/river_thresh.md) (m),
- $H$ is the channel water stage (m), and
- $D$ is the channel depth (`m`; the channel's `chd`, or the day's value from `chan_depth.gw`).

SWAT+ then computes the groundwater–channel exchange with Darcy's law:

$$Q = K \, \frac{\Delta h}{b} \, W \, L$$

where:
- $Q$ is the flow into the aquifer ($\text{m}^3/\text{day}$; negative is discharge to the channel),
- $K$ is the streambed hydraulic conductivity (`m/day`),
- $\Delta h$ is the head difference (m),
- $b$ is the streambed thickness (m),
- $W$ is the channel width (`chw`, m), and
- $L$ is [chan_length](chan_length.md) (m).

The head difference $\Delta h$ is taken as:

* $D$ when the head is below the bed ($h < z_{b}$): seepage driven by the full channel depth;
* $H - h$ when the head is between the bed and the stage: seepage;
* $H - h$, which is negative, when the head is above the stage: discharge to the channel.

The head exactly at $z_{b}$ or $H$ gives no exchange. Seepage is limited to the water in the channel and discharge to the water stored in the cell ([`gwflow_channel_exch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L89-L100)).
