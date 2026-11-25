---
description: "Reaction loss and metabolite production in water"
---

# metab_h2o_kg

**Code reference:** `chpst_d(j)%pest(ipest)%metab` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_pesticide_module.f90#L15)).

The channel stores water-column metabolite formation on the daughter pesticide's row. The reservoir also adds its sediment-branch calculation to this slot using water reaction loss as the parent mass. It adds the entire accumulated value to storage each time, so retained or earlier contributions can enter storage again. [Channel daughter increment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L130-L140), [Reservoir water branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L77-L86), [Reservoir sediment branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L150-L159).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-reservoir-pesticide-balance.md).
