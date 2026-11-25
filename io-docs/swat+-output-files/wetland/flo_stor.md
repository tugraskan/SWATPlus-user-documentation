---
description: "Water stored in the wetland"
---

# flo_stor

**Code reference:** `wet(j)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Water stored in the wetland.

**Unit:** m3.

The writer uses the current `wet(j)%flo` for every interval, including the average-annual row at simulation end. [Daily and longer-period records](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L20)

[Back to the output table](README.md).
