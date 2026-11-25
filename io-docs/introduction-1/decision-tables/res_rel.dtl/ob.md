---
description: "Object-type label for the condition"
---

# ob

**Code reference:** `dtbl_res(i)%cond(ic)%ob` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L9)).

Object-type label for the condition row. Most condition keywords choose the model array themselves, so this label does not change which object is read. Use `res` or `hru` for readability. `phu_base0`, `precip_cur`, and `precip_next` are exceptions: they need `hru` or `hlt` to turn [ob_num](ob_num.md) into a spatial object. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L145-L187)
