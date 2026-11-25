---
description: "Nitrogen transferred from the aquifer to the soil by the GWFlow module"
---

# gwsoiln

**Code reference:** `bnb_d%gwsoiln` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L101)).

Nitrate nitrogen transferred from groundwater to the soil profile when GWFlow soil transfer and solutes are enabled. The nitrate transport routine adds the transfer to each layer's nitrate pool and sums it for the HRU record. [layer mass transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_soil.f90#L108-L114), [nitrate pool and diagnostic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L59-L66).

**Unit:** kg N/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
