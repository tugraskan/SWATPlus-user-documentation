---
description: "Phosphorus transferred from the aquifer to the soil by the GWFlow module"
---

# gwsoilp

**Code reference:** `bnb_d%gwsoilp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L102)).

Phosphorus transferred from groundwater to the soil profile when GWFlow soil transfer and solutes are enabled. The phosphorus transport routine adds the transfer to each layer's labile P pool and sums it for the HRU record. [layer mass transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_soil.f90#L108-L114), [labile P pool and diagnostic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_solp.f90#L49-L56).

**Unit:** kg P/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
