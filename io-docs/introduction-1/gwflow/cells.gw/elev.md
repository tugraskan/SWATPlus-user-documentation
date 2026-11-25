---
description: "Ground-surface elevation, m"
---

# elev

**Code reference:** `gw_state(i)%elev` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L50), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L449)).

Ground-surface elevation of the cell, in m. It is the top of the aquifer: the bottom is $z - b$, where $b$ is [thck](thck.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L460)). It is also the reference surface for groundwater ET ([exdp](exdp.md)), saturation-excess flow, soil transfer, tile drain depth and floodplain stage. For reservoir exchange, the elevation of the reservoir's own cell is used as the reservoir head ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1153)).
