---
description: "Concentration in canal seepage water, g/m³"
---

# canal_out_conc

**Code reference:** `canal_out_conc(s)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L368), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1657)).

Concentration of the solute, in g/m³, in water that seeps from canals into cells. It applies to canals fed by a point-source diversion and to canals fed from outside the model ([`gwflow_canal_div.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal_div.f90#L144-L147), [`gwflow_canal_ext.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal_ext.f90#L113-L115)). Water moving from a cell to a canal carries the cell's concentration instead.
