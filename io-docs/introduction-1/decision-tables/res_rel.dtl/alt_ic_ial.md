---
description: "Alternative value for condition ic and alternative ial"
---

# alt(ic,ial)

**Code reference:** `dtbl_res(i)%alt(ic,ial)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L34)).

Enter one comparison per alternative. Numeric conditions recognize `<`, `>`, `<=`, `>=`, `=`, and `/=` (not equal). A hyphen skips the numeric comparison. Write the inequality token as `'/='` in the input file so its leading slash is read as data. [`cond_real.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cond_real.f90#L19-L52) · [`cond_integer.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cond_integer.f90#L15-L48)

Category and probability conditions treat these tokens differently, and several filter only on `=`; see [lum.dtl alt](../lum.dtl/alt.md).
