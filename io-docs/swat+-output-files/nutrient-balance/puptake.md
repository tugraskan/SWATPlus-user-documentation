---
description: "Plant phosphorus uptake"
---

# puptake

**Code reference:** `bnb_d%puptake` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L100)).

Phosphorus added to plant biomass from labile P in the root zone. Every plant uptake call clears the diagnostic, and a call with demand below `1.e-6` can leave it at zero even after an earlier plant took up phosphorus. [plant uptake](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_pup.f90#L52-L81).

**Unit:** kg P/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
