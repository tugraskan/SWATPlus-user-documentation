---
description: "Incoming water volume"
---

# flo_in

**Code reference:** `wet_in_d(j)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Incoming water volume.

**Unit:** m3.

Monthly output gives the average daily incoming volume in m3 per day. The yearly row uses the full accumulated volume in m3, and average annual divides the yearly volumes by the number of printed years. GWFlow can add groundwater inflow to the daily record when active. [Period calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L37), [Groundwater inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L139)

[Back to the output table](README.md).
