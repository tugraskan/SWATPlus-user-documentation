---
description: "Initial solute concentration, g/m³"
---

# conc

**Code reference:** `gwsol_state(i)%solute(s)%conc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L518), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1672)).

Initial concentration of each solute in the cell's groundwater, in g/m³, in solute order. The initial mass of active cells is ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2226-L2240)):

$$m = A \, (h - z_{\text{bot}}) \, S_{y} \, C$$

where $A$ is the cell area, $h$ the initial head, $z_{\text{bot}}$ the aquifer bottom, $S_{y}$ the specific yield and $C$ this value.
