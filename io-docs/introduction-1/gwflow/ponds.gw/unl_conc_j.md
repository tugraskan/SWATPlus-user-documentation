---
description: "Concentration of outside water, one per solute"
---

# unl_conc(j)

**Code reference:** `gw_pond_info(i)%unl_conc(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L422), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1957)).

Solute concentrations, in g/m³, of water supplied from outside the model (`unl` = 1), one value per solute ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1957), [`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L191-L220)). Solutes are always in this order: nitrate (`no3`), phosphorus (`p`), then the salt ions and the other constituents named in `constituents.cs`, in that file's order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1609-L1639)). When solute transport is off, no values are read.
