---
description: "Reaction loss and metabolite production"
---

# metab_kg

**Code reference:** `aqupst_d(j)%pest(ipest)%metab` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_module.f90#L11)).

Daughter pesticide formed from a parent's reaction loss, using the soil formation fraction and the daughter-to-parent molecular-weight ratio. The daily reporter is sensitive to the order of the parent and daughter in the configured pesticide list. [Daughter increment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L317-L336).

**Unit:** kg.

The daily 1-D aquifer routine adds each parent's production to the daughter pesticide's output record. It also zeros the current pesticide's `metab` field when that pesticide's iteration begins. A daughter processed later in the loop can lose an earlier parent's contribution from this diagnostic, even though the earlier increment was added to storage. [Metabolite loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L306)

[Back to schema](aquifer-pesticide-balance.md).
