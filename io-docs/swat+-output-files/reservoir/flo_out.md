---
description: "Flow out of the reservoir"
---

# flo_out

**Code reference:** `res_out_d(j)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Flow out of the reservoir.

**Unit:** m3.

Outflow is reported as a water volume. The monthly and yearly rows contain sums. Average annual divides the yearly outflow volumes by `time%yrs_prt`. Basin rows sum reservoir outflows. [Individual periods](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L29), [Basin aggregation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_reservoir_output.f90#L20)

[Back to the output table](README.md).
