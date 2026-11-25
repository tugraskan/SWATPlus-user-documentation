---
description: "Flashiness index"
---

# flash_idx

**Code reference:** `ob(icmd)%flash_idx%index` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L331)).

On each day the accumulator adds the signed difference between current and previous outflow. With the previous flow initialized to zero, those differences telescope to the last included day's flow, apart from floating-point rounding. The output divides that sum by the sum of included daily outflows if it exceeds `1.e-6` m³. The final day's flow is excluded from both sums because the report is written before the accumulator update on that day. [Accumulator defaults](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L326-L332), [call and update order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L412-L419), [report calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L139-L146).

This field has no physical unit in the output table.

[Back to the output table](README.md).
