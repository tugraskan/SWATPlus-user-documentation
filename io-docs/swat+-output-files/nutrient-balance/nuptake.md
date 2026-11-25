---
description: "Plant nitrogen uptake"
---

# nuptake

**Code reference:** `bnb_d%nuptake` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L99)).

The uptake routine adds fixed nitrogen to its soil nitrate uptake accumulator before assigning the printed result. Every plant call clears the diagnostic, and a call with demand below `1.e-6` can leave the value at zero even after an earlier plant took up nitrogen. [uptake and fixation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_nup.f90#L61-L100).

**Unit:** kg N/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
