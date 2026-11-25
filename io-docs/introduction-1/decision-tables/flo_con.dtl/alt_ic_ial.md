---
description: "Comparison token for each alternative"
---

# alt(ic,ial)

**Code reference:** `dtbl_flo(i)%alt(ic,ial)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L34)).

Comparison token for condition row `ic` in alternative `ial`; enter one per alternative. Numeric conditions use `<`, `>`, `<=`, `>=`, `=`, or `'/='`, and a hyphen skips them. Category conditions behave differently; see [lum.dtl alt](../lum.dtl/alt.md). [`cond_real.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cond_real.f90#L19-L52)
