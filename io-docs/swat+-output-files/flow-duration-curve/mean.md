---
description: "Equal-weight mean of annual values calculated with an extra day in the divisor"
---

# mean

**Code reference:** `ob(icmd)%fdc%p_md%mean` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L301)).

The annual calculation sums N day slots, then uses the loop counter after the loop, giving an N+1 divisor. The report gives every annual value equal weight, including a partial year, and divides the result by 86,400 to convert to m³/s. [Annual calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L58-L62), [across-year average](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L104-L112), [conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L133-L136).

**Unit:** m3/s.

This field belongs to a fixed or event-style report rather than the standard daily/monthly/yearly/average-annual series.

[Back to the output table](README.md).
