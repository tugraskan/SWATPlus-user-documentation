---
description: "Aquifer thickness, m"
---

# thck

**Code reference:** `gw_state(i)%thck` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L51), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L450)).

Aquifer thickness, in m. The aquifer bottom is $z - b$, where $z$ is [elev](elev.md) and $b$ is this value ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L460)). Saturated thickness is the head minus the bottom; it is 0 when the head is at or below the bottom, and then no ET or pumping is taken from the cell.
