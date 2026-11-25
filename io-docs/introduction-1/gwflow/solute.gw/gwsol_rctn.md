---
description: "First-order reaction rate, 1/day"
---

# gwsol_rctn

**Code reference:** `gwsol_rctn(s)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L511), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1657)).

First-order reaction rate of the solute, in 1/day. The reaction mass per day is ([`gwflow_chem.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_chem.f90#L45-L51)):

$$m_{\text{rct}} = C \, V \, k$$

where $C$ is the concentration (g/m³), $V$ the groundwater volume in the cell (m³) and $k$ this rate. The result is added to the cell, so a negative rate is decay (for example denitrification of nitrate) and a positive rate is production. For selenium species, reaction rates come from the constituent chemistry instead.
