---
description: "Signed transfer between active and stable organic nitrogen pools"
---

# act_sta_n

**Code reference:** `bnb_d%act_sta_n` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L91)).

In `cswat = 0`, positive values move nitrogen from active to stable organic N and negative values move it in the reverse direction. The SWAT-C residue routine clears this legacy diagnostic and the modern pool calculations leave it at zero. [static soil transfer](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/nut_nminrl.f90#L105-L115), [SWAT-C reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_rsd_transfer.f90#L58-L64).

**Unit:** kg N/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
