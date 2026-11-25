---
description: "Saturation-excess groundwater flow to channels (1 = on)"
---

# satx

**Code reference:** `gw_satx_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L227), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L244)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on, groundwater above the ground surface leaves the cell as surface flow to a channel ([`gwflow_satexcess.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_satexcess.f90#L48-L60)):

$$V = A \, (h - z) \, S_{y} \quad \text{when} \; h > z$$

where $A$ is the cell area (m²), $h$ the head, $z$ the ground elevation (m) and $S_{y}$ the specific yield. The water goes to the channel of the channel cell nearest to the cell centroid ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L839-L860)).
