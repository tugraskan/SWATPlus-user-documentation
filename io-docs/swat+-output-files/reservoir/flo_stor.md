---
description: "Flow storage in the reservoir"
---

# flo_stor

**Code reference:** `res(j)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Flow storage in the reservoir.

**Unit:** m3.

Stored water volume on the reporting date. Monthly, yearly, and average-annual rows still use the current storage record. The basin row sums the reservoirs' current stored volumes. [Individual period write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L78), [Basin aggregation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_reservoir_output.f90#L20)

[Back to the output table](README.md).
