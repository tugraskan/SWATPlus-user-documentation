---
description: Bacteria removal by BMP (not applied in SWAT+ main (6f515368))
---

# bact\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_bac` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L67)).

In SWAT+ main (6f515368), this value is read from bmpuser.str and copied to the HRU, but it is not used in any calculation. Changing this value does not change bacteria removal.
