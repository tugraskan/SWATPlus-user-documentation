---
description: "Pumping rate, m³/day"
---

# gw_pumpex_rates_tmp

**Code reference:** `gw_pumpex_rates_tmp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L141), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L983-L984)).

Volume pumped from the cell on each day of the period, in m³/day ([`gwflow_pump_ext.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pump_ext.f90#L43-L49)). If the cell holds less water, only the stored volume is taken. The water leaves the model.
