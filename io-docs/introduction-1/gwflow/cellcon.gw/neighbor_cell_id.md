---
description: "Neighbor cell number"
---

# neighbor_cell_id

**Code reference:** `cell_con(i)%cell_id(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L241), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L522-L524)).

Number of a cell that exchanges water with this one. Lateral flow, solute advection and dispersion, and heat conduction are computed for each listed pair ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L54-L93)). Connections are not made two-way automatically: list each cell in its neighbor's line as well. Cells around a reservoir cell exchange water with the reservoir through these lists ([`gwflow_reservoir.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L44-L51)).
