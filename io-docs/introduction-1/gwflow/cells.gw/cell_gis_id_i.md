---
description: "GIS identifier written to per-cell output"
---

# cell_gis_id(i)

**Code reference:** `cell_gis_id(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L44), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L447)).

GIS identifier of the cell's polygon. SWAT+ writes it in the `gis_id` column of per-cell GWFlow output ([`gwflow_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1227)); it does not affect the simulation.
