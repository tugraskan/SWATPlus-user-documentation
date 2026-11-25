---
description: "Benthic reaction, metabolite production, and burial"
---

# metab_benth_kg

**Code reference:** `chpst_d(j)%pest(ipest)%metab_bot` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_pesticide_module.f90#L21)).

The channel adds the newly formed daughter pesticide mass in the bed to this field. The reservoir producer leaves it at zero and uses `metab_h2o_kg` for its sediment-branch calculation. [Channel benthic production](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L225-L235), [Reservoir sediment-branch assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L150-L159).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-reservoir-pesticide-balance.md).
