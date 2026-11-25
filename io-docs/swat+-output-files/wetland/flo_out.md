---
description: "Outgoing water volume"
---

# flo_out

**Code reference:** `wet_out_d(j)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Outgoing water volume.

**Unit:** m3.

Monthly output gives the average daily outgoing volume in m3 per day. The yearly row uses the full accumulated volume in m3, and average annual divides the yearly volumes by the number of printed years. Paddy discharge uses a weir release routine, while other wetlands use the configured decision table. [Period calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L37), [Release paths](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L179)

[Back to the output table](README.md).
