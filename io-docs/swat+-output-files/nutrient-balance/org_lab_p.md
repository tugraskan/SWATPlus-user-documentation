---
description: "Phosphorus moving from the organic pool to labile pool"
---

# org_lab_p

**Code reference:** `bnb_d%org_lab_p` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L92)).

In the static carbon routine, the recorded transfer draws from the stable humus P pool and adds to labile P. The SWAT-C residue routine clears this legacy diagnostic and the modern transformations leave it at zero. [static humus P transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L129-L145), [SWAT-C reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_rsd_transfer.f90#L58-L64).

**Unit:** kg/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
