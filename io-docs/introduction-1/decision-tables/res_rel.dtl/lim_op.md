---
description: "Operator applied when comparing the condition variable to the limit variable (*, +, -)"
---

# lim_op

**Code reference:** `dtbl_res(i)%cond(ic)%lim_op` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L12)).

Arithmetic operator that builds a threshold from a named quantity $v$ and the constant $c$. It is used by `soil_water`, `vol` (with `pvol` or `evol`), and `vol_wet`. `*` gives $vc$ and `/` gives $v/c$; write division as `'/'`. For `+` and `-`, `soil_water` adds $c$ in mm and `vol_wet` adds $c$ in m³, but `vol` adds $10000c$ m³, so enter ha-m there. `vol` with `e-pv` ignores the operator and uses $V_p + c(V_e - V_p)$, where $V_p$ and $V_e$ are principal and emergency storage. Other conditions ignore this column. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L298-L308) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L749-L779) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L832-L842)
