---
description: Soluble P removal by BMP
---

# solp\_eff

**Code reference:** `bmpuser_db(ibmpop)%bmp_sp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L64)).

Enter the fraction of soluble phosphorus removed by this BMP (`0.0–1.0`; e.g., `0.2` removes 20%). In [`smp_bmpfixed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_bmpfixed.f90#L53), SWAT+ reduces surface runoff soluble P (`surqsolp`) by:

$$L_{\text{out}} = L_{\text{in}} \cdot (1 - E_{\text{sp}})$$

where $L_{\text{in}}$ and $L_{\text{out}}$ are surface runoff soluble P before and after BMP removal, and $E_{\text{sp}}$ is `solp_eff`.
