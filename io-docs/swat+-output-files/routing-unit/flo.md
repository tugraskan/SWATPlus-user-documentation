---
description: "Routing-unit water volume"
---

# flo

**Code reference:** `ru_d(iru)%flo` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_output.f90#L24); [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Water volume summed across the routing-unit element hydrograph slots. For a full HRU, the sum includes its total outflow, individual surface, lateral, and tile flows, and recharge. The total already contains the three outflow components. [Report accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L122-L149), [full-HRU total](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L165-L169).

**Unit:** m3.

Daily volume and constituent mass values are added into monthly and yearly totals; the average-annual record divides accumulated volume and masses by `time%yrs_prt`. The [hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337) combine temperature by water-volume weighting, and division by years leaves temperature unchanged. The writers perform no volume-to-rate conversion. The printed units row says `m^3/s`; the source component is volume, and the writer applies no division by 86400.

[Back to the output table](README.md).
