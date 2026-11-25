---
description: Bacteria removal by BMP (not applied in SWAT+ main (6f515368))
---

# bact\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_bac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L67)).

In SWAT+ main (6f515368), this value is read from bmpuser.str and copied to the HRU, but it is not used in any calculation. Changing this value does not change bacteria removal.
